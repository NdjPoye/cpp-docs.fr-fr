---
title: "/GS (v&#233;rification de la s&#233;curit&#233; des m&#233;moires tampons) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLWCECompilerTool.BufferSecurityCheck"
  - "VC.Project.VCCLCompilerTool.BufferSecurityCheck"
  - "/GS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "mémoires tampons [C++], dépassements de mémoire tampon"
  - "dépassements de mémoire tampon, commutateur /GS du compilateur"
  - "GS, option du compilateur [C++]"
  - "/GS, option du compilateur [C++]"
  - "vérification de la sécurité, option du compilateur [C++]"
  - "-GS, option du compilateur [C++]"
  - "mémoires tampons [C++], éviter les dépassements"
ms.assetid: 8d8a5ea1-cd5e-42e1-bc36-66e1cd7e731e
caps.latest.revision: 40
caps.handback.revision: 40
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /GS (v&#233;rification de la s&#233;curit&#233; des m&#233;moires tampons)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Détecte des dépassements de mémoire tampon qui remplacent l'adresse de retour d'une fonction, l'adresse de gestionnaire d'exceptions ou certains types de paramètres.  Provoquer un dépassement de mémoire tampon est une technique utilisée par les pirates informatiques pour exploiter du code qui n'applique pas de restrictions de taille de mémoire tampon.  
  
## Syntaxe  
  
```  
/GS[-]  
```  
  
## Notes  
 **\/GS** est activé par défaut.  Si votre application ne doit normalement avoir aucune exposition en termes de sécurité, utilisez **\/GS\-**.  Pour plus d'informations sur **\/GS**, consultez[Vérifications détaillées de la sécurité du compilateur](http://go.microsoft.com/fwlink/?linkid=7260).  Pour plus d'informations sur la suppression de la détection de dépassement de mémoire tampon, consultez [safebuffers](../../cpp/safebuffers.md).  
  
## Vérifications de la sécurité  
 Sur les fonctions que le compilateur reconnaît comme sujettes à des problèmes de dépassement de mémoire tampon, le compilateur attribue l'espace sur la pile avant l'adresse de retour.  À l'entrée de la fonction, l'espace alloué est chargé avec un *cookie de sécurité* qui est calculé une fois lors du chargement du module.  À la sortie d'une fonction, et pendant le déroulement des frames sur les systèmes d'exploitation 64 bits, une fonction d'assistance est appelée pour s'assurer que la valeur du cookie est encore la même.  Une valeur différente indique qu'un remplacement de la pile a pu se produire.  Si une valeur différente est détectée, le processus est terminé.  
  
## Mémoires tampon GS  
 Une vérification de sécurité de dépassement de mémoire tampon est exécutée sur une *mémoire tampon GS*.  Une mémoire tampon GS peut être l'une de celles\-ci :  
  
-   Un tableau qui est supérieur à 4 octets, a plus de deux éléments et possède un type d'élément qui n'est pas un type de pointeur.  
  
-   Structure de données dont la taille est plus de 8 octets et ne contient pas de pointeurs.  
  
-   Mémoire tampon allouée à l'aide de la fonction [\_alloca](../../c-runtime-library/reference/alloca.md).  
  
-   Toute classe ou structure qui contient une mémoire tampon GS.  
  
 Par exemple, les instructions suivantes déclarent des mémoires tampon GS.  
  
```  
char buffer[20];  
int buffer[20];  
struct { int a; int b; int c; int d; } myStruct;  
struct { int a; char buf[20]; };  
```  
  
 Toutefois, les instructions suivantes ne déclarent pas de mémoires tampon GS.  Les deux premières déclarations contiennent des éléments de type pointeur.  Les troisième et quatrième instructions déclarent des tableaux dont la taille est trop petite.  La cinquième instruction déclare une structure dont la taille sur une plateforme x86 ne dépasse pas 8 octets.  
  
```  
char *pBuf[20];  
void *pv[20];  
char buf[4];  
int buf[2];  
struct { int a; int b; };  
```  
  
## Initialiser le cookie de sécurité  
 L'option de compilateur **\/GS** requiert que le cookie de sécurité soit initialisé avant l'exécution de toute fonction utilisant le cookie.  Le cookie de sécurité doit être initialisé à l'entrée sur un EXE ou une DLL.  Cela est fait automatiquement si vous utilisez les points d'entrée CRT par défaut \(mainCRTStartup, wmainCRTStartup, WinMainCRTStartup, wWinMainCRTStartup ou \_DllMainCRTStartup\).  Si vous utilisez un autre point d'entrée, vous devez initialiser manuellement le cookie de sécurité en appelant [\_\_security\_init\_cookie](../../c-runtime-library/reference/security-init-cookie.md).  
  
## Ce qui est protégé  
 L'option de compilateur **\/GS** protège les éléments suivants :  
  
-   Adresse de retour d'un appel de fonction.  
  
-   Adresse d'un gestionnaire d'exceptions pour une fonction.  
  
-   Paramètres de fonction vulnérables.  
  
 Sur toutes les plateformes, tentatives **\/GS** de détecter des dépassements de mémoire tampon dans l'adresse de retour.  Les dépassements de mémoire tampon sont exploités plus facilement sur les plateformes comme x86 et x64, qui utilisent des conventions d'appel qui stockent l'adresse de retour d'un appel de fonction sur la pile.  
  
 Sur x86, si une fonction utilise un gestionnaire d'exceptions, le compilateur injecte un cookie de sécurité pour protéger l'adresse du gestionnaire d'exceptions.  Le cookie est vérifié pendant le déroulement de frame.  
  
 **\/GS** protège les *paramètres vulnérables* passés dans une fonction.  Un paramètre vulnérable est un pointeur, une référence C\+\+, une structure C \(type POD C\+\+\) qui contient un pointeur, ou une mémoire tampon GS.  
  
 Les paramètres vulnérables sont alloués avant le cookie et les variables locales.  Un dépassement de mémoire tampon peut remplacer ces paramètres.  Et du code dans la fonction qui utilise ces paramètres pourrait provoquer une attaque avant que la fonction ne soit retournée et que la vérification de la sécurité ne soit exécutée.  Pour minimiser ce danger, le compilateur fait une copie des paramètres vulnérables pendant le prologue de fonction et les place sous la zone de stockage pour toutes les mémoires tampon.  
  
 Le compilateur ne copie pas les paramètres vulnérables dans les situations suivantes :  
  
-   Fonctions qui ne contiennent pas de mémoire tampon GS.  
  
-   Les optimisations \([options \/O](../../build/reference/o-options-optimize-code.md)\) ne sont pas activées.  
  
-   Fonctions qui ont une liste d'arguments variable \(...\).  
  
-   Fonctions marquées avec [naked](../../cpp/naked-cpp.md).  
  
-   Fonctions qui contiennent le code assembleur inline dans la première instruction.  
  
-   Un paramètre est utilisé uniquement de façon à être le moins exploitable possible en cas de dépassement de mémoire tampon.  
  
## Ce qui n'est pas protégé  
 L'option de compilateur **\/GS** ne protège pas contre toutes les attaques de sécurité de dépassement de mémoire tampon.  Par exemple, si vous avez une mémoire tampon et un vtable dans un objet, un dépassement de mémoire tampon peut endommager le vtable.  
  
 Même si vous utilisez **\/GS**, essayez toujours d'écrire du code sécurisé qui n'a pas de dépassements de mémoire tampon.  
  
#### Pour définir cette option de compilateur dans Visual Studio.  
  
1.  Dans l'**Explorateur de solutions**, cliquez avec le bouton droit sur le projet, puis cliquez sur **Propriétés**.  
  
     Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Dans la boîte de dialogue **Pages de propriétés**, cliquez sur le dossier **C\/C\+\+**.  
  
3.  Cliquez sur la page de propriétés **Génération de code**.  
  
4.  Modifiez la propriété **Vérification de la sécurité de la mémoire tampon**.  
  
#### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.BufferSecurityCheck%2A>.  
  
## Exemple  
 Cet exemple provoque un dépassement de la mémoire tampon.  Dans ce cas, l'application échoue au moment de l'exécution.  
  
```  
// compile with: /c /W1  
#include <cstring>  
#include <stdlib.h>  
#pragma warning(disable : 4996)   // for strcpy use  
  
// Vulnerable function  
void vulnerable(const char *str) {  
   char buffer[10];  
   strcpy(buffer, str); // overrun buffer !!!  
  
   // use a secure CRT function to help prevent buffer overruns  
   // truncate string to fit a 10 byte buffer  
   // strncpy_s(buffer, _countof(buffer), str, _TRUNCATE);  
}  
  
int main() {  
   // declare buffer that is bigger than expected  
   char large_buffer[] = "This string is longer than 10 characters!!";  
   vulnerable(large_buffer);  
}  
```  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)
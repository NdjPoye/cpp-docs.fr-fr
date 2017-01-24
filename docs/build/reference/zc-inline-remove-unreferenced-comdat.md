---
title: "/Zc:inline (supprimer des &#233;l&#233;ments COMDAT non r&#233;f&#233;renc&#233;s) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/Zc:inline"
  - "VC.Project.VCCLCompilerTool.RemoveUnreferencedCodeData"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Zc (options du compilateur C++)"
  - "/Zc:inline"
  - "Zc (options du compilateur C++)"
  - "-Zc (options du compilateur C++)"
ms.assetid: a4c94224-1d73-4bea-a9d5-4fa73dc924df
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Zc:inline (supprimer des &#233;l&#233;ments COMDAT non r&#233;f&#233;renc&#233;s)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Supprime les données ou fonctions non référencées qui sont des COMDAT ou qui possèdent uniquement une liaison interne.  Quand **\/Zc:inline** est spécifié, le compilateur exige que les unités de traduction qui utilisent des données inline ou des fonctions inline incluent également les définitions relatives à ces données ou fonctions.  
  
## Syntaxe  
  
```  
/Zc:inline[-]  
```  
  
## Notes  
 Quand **\/Zc:inline** est spécifié, le compilateur n'émet pas d'informations de symbole pour les données ou fonctions COMDAT non référencées, ni pour les données ou fonctions qui possèdent uniquement une liaison interne.  Cette option est désactivée par défaut \(**\/Zc:inline\-**\).  Cette optimisation simplifie une partie du travail effectué par l'éditeur de liens dans les versions Release ou quand l'option de l'éditeur de liens [\/OPT:REF](../../build/reference/opt-optimizations.md) est spécifiée.  Quand le compilateur effectue cette optimisation, il peut réduire considérablement la taille du fichier .obj et accélérer le fonctionnement de l'éditeur de liens.  Cette option du compilateur n'est pas activée quand les optimisations sont désactivées \([\/Od](../../build/reference/od-disable-debug.md)\) ou quand [\/GL \(Optimisation de l'ensemble du programme\)](../../build/reference/gl-whole-program-optimization.md) est spécifié.  
  
 Si **\/Zc:inline** est spécifié, le compilateur applique la spécification C\+\+11 stipulant que toutes les fonctions déclarées `inline` doivent avoir une définition disponible dans la même unité de traduction si elles sont utilisées.  Quand cette option n'est pas spécifiée, [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] autorise du code non conforme qui appelle des fonctions déclarées `inline` même si aucune définition n'est visible.  Pour plus d'informations, voir la norme C\+\+11, section 3.2 et section 7.1.2.  Cette option du compilateur a été introduite pour la première fois dans Visual Studio 2013 Update 2.  
  
 Pour pouvoir utiliser l'option **\/Zc:inline**, mettez à jour le code non conforme.  Cet exemple illustre comment l'utilisation non conforme d'une déclaration de fonction inline sans définition est encore compilée et liée quand l'option **\/Zc:inline\-** par défaut est utilisée :  
  
```cpp  
// example.h  
// Compile by using: cl /W4 /EHsc /O2 zcinline.cpp example.cpp  
#pragma once  
  
class Example {  
public:  
   inline void inline_call(); // declared but not defined inline  
   void normal_call();  
   Example() {};  
};  
```  
  
```cpp  
// example.cpp  
// Compile by using: cl /W4 /EHsc /O2 zcinline.cpp example.cpp  
#include <stdio.h>  
#include "example.h"  
  
void Example::inline_call() {  
   printf("inline_call was called.\n");   
}  
  
void Example::normal_call() {  
   printf("normal_call was called.\n");   
   inline_call(); // with /Zc:inline-, inline_call forced into .obj file  
}  
```  
  
```cpp  
// zcinline.cpp  
// Compile by using: cl /W4 /EHsc /O2 zcinline.cpp example.cpp  
#include "example.h"  
  
void main() {  
   Example example;  
   example.inline_call(); // normal call when definition unavailable  
}  
```  
  
 Quand **\/Zc:inline** est activé, le même code génère une erreur [LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md), car le compilateur n'émet pas de corps de code non inline pour `Example::inline_call` dans example.obj.  Par conséquent, l'appel non inline dans `main` référence un symbole externe non défini.  
  
 Pour résoudre cette erreur, vous pouvez supprimer le mot clé `inline` de la déclaration de `Example::inline_call`, placer la définition de `Example::inline_call` dans le fichier d'en\-tête ou placer l'implémentation de `Example` dans main.cpp.  Dans l'exemple suivant, la définition est placée dans le fichier d'en\-tête, où elle est visible pour tout appelant qui inclut l'en\-tête.  
  
```cpp  
// example2.h  
// Compile by using: cl /W4 /EHsc /O2 zcinline2.cpp example2.cpp  
#pragma once  
#include <stdio.h>  
  
class Example2 {  
public:  
   inline void inline_call() {  
      printf("inline_call was called.\n");   
   }  
   void normal_call();  
   Example2() {};  
};  
```  
  
```cpp  
// example2.cpp  
// Compile by using: cl /W4 /EHsc /O2 zcinline2.cpp example2.cpp  
#include "example2.h"  
  
void Example2::normal_call() {  
   printf("normal_call was called.\n");   
   inline_call();   
}  
```  
  
```cpp  
// zcinline2.cpp  
// Compile by using: cl /W4 /EHsc /O2 zcinline2.cpp example2.cpp  
#include "example2.h"  
  
void main() {  
   Example2 example2;  
   example2.inline_call(); // normal call when definition unavailable  
}  
```  
  
 Pour plus d'informations sur les problèmes de conformité dans Visual C\+\+, consultez [Comportement non standard](../../cpp/nonstandard-behavior.md).  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, voir [Utilisation des propriétés de projet](../../ide/working-with-project-properties.md).  
  
2.  Sélectionnez le dossier **C\/C\+\+**.  
  
3.  Sélectionnez la page de propriétés **Ligne de commande**.  
  
4.  Modifiez la propriété **Options supplémentaires** pour inclure `/Zc:inline`, puis choisissez **OK**.  
  
## Voir aussi  
 [\/Zc \(Conformité\)](../../build/reference/zc-conformance.md)
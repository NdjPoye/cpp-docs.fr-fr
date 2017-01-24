---
title: "/Gd, /Gr, /Gv, /Gz (Convention d&#39;appel) | Microsoft Docs"
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
  - "/gr"
  - "/Gv"
  - "/gz"
  - "/Gd"
  - "VC.Project.VCCLCompilerTool.CallingConvention"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Gd (option du compilateur C++)"
  - "/Gr (option du compilateur C++)"
  - "/Gv (option du compilateur C++)"
  - "/Gz (option du compilateur C++)"
  - "Gd (option du compilateur C++)"
  - "-Gd (option du compilateur C++)"
  - "Gr (option du compilateur C++)"
  - "-Gr (option du compilateur C++)"
  - "Gv (option du compilateur C++)"
  - "-Gv (option du compilateur C++)"
  - "Gz (option du compilateur C++)"
  - "-Gz (option du compilateur C++)"
ms.assetid: fd3110cb-2d77-49f2-99cf-a03f9ead00a3
caps.latest.revision: 19
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Gd, /Gr, /Gv, /Gz (Convention d&#39;appel)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ces options déterminent l'ordre dans lequel les arguments de fonction font l'objet d'un push sur la pile ; si la fonction appelante ou la fonction appelée supprime les arguments de la pile à la fin de l'appel ; et la convention de décoration de nom que le compilateur utilise pour identifier différentes fonctions.  
  
## Syntaxe  
  
```  
/Gd  
/Gr  
/Gv  
/Gz  
```  
  
## Notes  
 **\/Gd**, le paramètre par défaut, spécifie la convention d'appel [\_\_cdecl](../../cpp/cdecl.md) pour toutes les fonctions, sauf les fonctions membres C\+\+ et les fonctions qui sont marquées [\_\_stdcall](../../cpp/stdcall.md), [\_\_fastcall](../../cpp/fastcall.md) ou [\_\_vectorcall](../../cpp/vectorcall.md).  
  
 **\/Gr** spécifie la convention d'appel `__fastcall` pour toutes les fonctions, sauf les fonctions membres C\+\+, les fonctions nommées `main` et les fonctions qui sont marquées `__cdecl`, `__stdcall` ou `__vectorcall`.  Toutes les fonctions `__fastcall` doivent avoir des prototypes.  Cette convention d'appel est uniquement disponible dans les compilateurs qui ciblent x86 et est ignorée par les compilateurs qui ciblent d'autres architectures.  
  
 **\/Gz** spécifie la convention d'appel `__stdcall` pour toutes les fonctions, sauf les fonctions membres C\+\+, les fonctions nommées `main` et les fonctions qui sont marquées `__cdecl`, `__fastcall` ou `__vectorcall`.  Toutes les fonctions `__stdcall` doivent avoir des prototypes.  Cette convention d'appel est uniquement disponible dans les compilateurs qui ciblent x86 et est ignorée par les compilateurs qui ciblent d'autres architectures.  
  
 **\/Gv** spécifie la convention d'appel `__vectorcall` pour toutes les fonctions à l'exception des fonctions membres C\+\+, fonctions nommées principal, fonctions dotées d'une liste d'arguments de variable `vararg` ou fonctions qui sont marquées d'un attribut `__cdecl`, `__stdcall` ou  `__fastcall` en conflit.  Cette convention d'appel est uniquement disponible sur les architectures x86 et x64 qui prennent en charge \/arch:SSE2 et supérieures, et est ignorée par les compilateurs qui ciblent l'architecture ARM.  
  
 Les fonctions qui acceptent un nombre variable d'arguments doivent être marquées `__cdecl`.  
  
 **\/Gd**, **\/Gr**, **\/Gv** et **\/Gz** ne sont pas compatibles avec [\/clr:safe](../../build/reference/clr-common-language-runtime-compilation.md) ou **\/clr:pure**.  
  
> [!NOTE]
>  Par défaut pour les processeurs x86, les fonctions membres C\+\+ utilisent [\_\_thiscall](../../cpp/thiscall.md) par défaut.  
  
 Pour tous les processeurs, une fonction membre marquée explicitement comme `__cdecl`, `__fastcall`, `__vectorcall` ou `__stdcall` utilise la convention d'appel spécifiée si elle n'est pas ignorée dans cette architecture.  Une fonction membre qui accepte un nombre variable d'arguments utilise toujours la convention d'appel `__cdecl`.  
  
 Ces options de compilateur n'ont aucun effet sur la décoration de noms des méthodes et fonctions C\+\+.  Sauf si elles sont déclarées en tant que `extern "C"`, les fonctions et méthodes C\+\+ utilisent un mécanisme de décoration de noms différent.  Pour plus d'informations, consultez [Noms décorés](../../build/reference/decorated-names.md).  
  
 Pour plus d'informations sur les conventions d'appel, consultez [Conventions d'appel](../../cpp/calling-conventions.md).  
  
## Particularités \_\_cdecl  
 Pour les processeurs x86, tous les arguments de fonction sont passés sur la pile de droite à gauche.  Pour les architectures ARM et x64, certains arguments sont passés par le registre et les arguments restants sont passés sur la pile de droite à gauche.  La routine d'appel fait apparaître les arguments de la pile.  
  
 Pour C, la convention d'affectation de noms `__cdecl` utilise le nom de la fonction précédé d'un trait de soulignement \(`_`\) ; aucune conversion de casse n'est effectuée.  Sauf si elles sont déclarées en tant que `extern "C"`, les fonctions C\+\+ utilisent un mécanisme de décoration de noms différent.  Pour plus d'informations, consultez [Noms décorés](../../build/reference/decorated-names.md).  
  
## Particularités de \_\_fastcall  
 Certains des arguments d'une fonction `__fastcall`sont passés dans les registres \(pour les processeurs x86, ECX et EDX\), et les autres font l'objet d'un push sur la pile de droite à gauche.  La routine appelée dépile ces arguments avant de retourner.  En principe, **\/Gr** réduit le délai d'exécution.  
  
> [!NOTE]
>  Soyez vigilant lorsque vous utilisez la convention d'appel `__fastcall`pour une fonction écrite dans un langage assembleur inline.  L'utilisation des registres peut entrer en conflit avec celle du compilateur.  
  
 Pour C, la convention d'affectation de noms `__fastcall` utilise le nom de fonction précédé du signe arobase \(`@`\), suivi de la taille des arguments de la fonction en octets.  Aucune conversion de casse n'a lieu.  Le compilateur utilise ce modèle pour la convention d'affectation de noms :  
  
```c  
@function_name@number  
```  
  
 Lorsque vous utilisez la convention d'affectation de noms `__fastcall`, utilisez les fichiers include standard.  Autrement, vous pouvez obtenir des références externes non résolues.  
  
## Particularités de \_\_stdcall  
 Les arguments d'une fonction `__stdcall` font l'objet d'un push sur la pile de droite à gauche, et la routine appelée dépile ces arguments avant de retourner.  
  
 Pour C, la convention d'affectation de noms `__stdcall` utilise le nom de fonction précédé d'un trait de soulignement \(`_`\) suivi du signe arobase \(@\) et de la taille des arguments de la fonction en octets.  Aucune conversion de casse n'a lieu.  Le compilateur utilise ce modèle pour la convention d'affectation de noms :  
  
```c  
_functionname@number  
```  
  
## Caractéristiques spécifiques de \_\_vectorcall  
 Les arguments entiers d'une fonction `__vectorcall` sont transmis par valeur, utilisant jusqu'à deux \(sur x86\) ou quatre \(sur x64\) registres d'entiers, et jusqu'à six registres XMM pour les valeurs à virgule flottante et vectorielles. Le reste est transmis dans la pile de droite à gauche.  La fonction appelée nettoie la pile avant son retour.  Les valeurs de retour vectorielles et à virgule flottante sont retournées dans XMM0.  
  
 Pour C, la convention d'affectation de noms `__vectorcall` utilise le nom de fonction suivi de deux signes arobase \(@@\) et de la taille des arguments de la fonction en octets.  Aucune conversion de casse n'a lieu.  Le compilateur utilise ce modèle pour la convention d'affectation de noms :  
  
```c  
functionname@@number  
```  
  
### To set this compiler option in the Visual Studio development environment  
  
1.  Open the project's **Property Pages** dialog box.  For details, see [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Select the **C\/C\+\+** folder.  
  
3.  Select the **Advanced** property page.  
  
4.  Modify the **Calling Convention** property.  
  
### To set this compiler option programmatically  
  
-   See <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CallingConvention%2A>.  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)
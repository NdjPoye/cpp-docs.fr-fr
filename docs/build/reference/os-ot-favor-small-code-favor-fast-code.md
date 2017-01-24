---
title: "/Os, /Ot (Favoriser la taille du code, Favoriser la vitesse du code) | Microsoft Docs"
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
  - "VC.Project.VCCLWCECompilerTool.FavorSizeOrSpeed"
  - "/os"
  - "VC.Project.VCCLCompilerTool.FavorSizeOrSpeed"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Os (option du compilateur C++)"
  - "/Ot (option du compilateur C++)"
  - "code rapide"
  - "favoriser la vitesse du code (option du compilateur C++)"
  - "favoriser la taille du code (option du compilateur C++)"
  - "Os (option du compilateur C++)"
  - "-Os (option du compilateur C++)"
  - "Ot (option du compilateur C++)"
  - "-Ot (option du compilateur C++)"
  - "code machine compact"
ms.assetid: 9a340806-fa15-4308-892c-355d83cac0f2
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Os, /Ot (Favoriser la taille du code, Favoriser la vitesse du code)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Réduit ou agrandit la taille des fichiers EXE et des DLL.  
  
## Syntaxe  
  
```  
/Os  
/Ot  
```  
  
## Notes  
 **\/Os** \(Favoriser la taille du code\) réduit la taille des fichiers EXE et des DLL en indiquant au compilateur de favoriser la taille par rapport à la vitesse.  Le compilateur peut réduire de nombreuses constructions C et C\+\+ à des séquences de code machine au fonctionnement similaire.  Parfois, ces différences offrent des compromis taille\/vitesse.  Les options **\/Os** et **\/Ot** permettent de spécifier une préférence pour l'une par rapport à l'autre :  
  
 **\/Ot** \(Favoriser la vitesse du code\) augmente la vitesse des fichiers EXE et des DLL en indiquant au compilateur de favoriser la vitesse par rapport à la taille. \(Il s'agit du paramètre par défaut.\) Le compilateur peut réduire de nombreuses constructions C et C\+\+ à des séquences de code machine au fonctionnement similaire.  Parfois, ces différences offrent des compromis taille\/vitesse.  L'option \/Ot est implicite du fait de l'option[\/O2](../../build/reference/o1-o2-minimize-size-maximize-speed.md) \(Augmenter la vitesse\).  L'option **\/O2** combine plusieurs options pour produire un code très rapide.  
  
 Si vous utilisez **\/Os** ou **\/Ot**, vous devez également spécifier [\/Og](../../build/reference/og-global-optimizations.md) pour optimiser le code.  
  
> [!NOTE]
>  Les informations collectées à partir des séries de tests de profilage substituent les optimisations qui s'appliqueraient si vous spécifiez **\/Ob**, **\/Os** ou **\/Ot**.  Pour plus d'informations, consultez [Optimisations guidées par profil](../../build/reference/profile-guided-optimizations.md).  
  
 **Section spécifique à x86**  
  
 L'exemple de code suivant montre la différence entre les options **\/Os** \(Favoriser la taille du code\) et l'option **\/Ot** \(Favoriser la vitesse du code\) :  
  
> [!NOTE]
>  Les éléments suivants décrivent le comportement attendu lors de l'utilisation de **\/Os** ou **\/Ot**.  Cependant, le comportement du compilateur d'une version à une autre peut produire différentes optimisations pour le code ci\-dessous.  
  
```  
/* differ.c  
  This program implements a multiplication operator  
  Compile with /Os to implement multiply explicitly as multiply.  
  Compile with /Ot to implement as a series of shift and LEA instructions.  
*/  
int differ(int x)  
{  
    return x * 71;  
}  
```  
  
 Comme le montre le fragment de code machine ci\-dessous, quand DIFFER.c est compilé avec une option de taille \(**\/Os**\), le compilateur implémente l'expression de multiplication dans l'instruction de retour explicitement en tant que multiplication afin de produire une séquence de code courte, mais plus lente :  
  
```  
mov    eax, DWORD PTR _x$[ebp]  
imul   eax, 71                  ; 00000047H  
```  
  
 Sinon, quand DIFFER.c est compilé en fonction de la vitesse \(**\/Ot**\), le compilateur implémente l'expression de multiplication dans l'instruction de retour en tant que série d'instructions de décalage et `LEA` pour produire une séquence de code rapide, mais plus longue :  
  
```  
mov    eax, DWORD PTR _x$[ebp]  
mov    ecx, eax  
shl    eax, 3  
lea    eax, DWORD PTR [eax+eax*8]  
sub    eax, ecx  
```  
  
 **FIN Spécifique x86**  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Cliquez sur le dossier **C\/C\+\+**.  
  
3.  Cliquez sur la page de propriétés **Optimisation**.  
  
4.  Modifiez la propriété **Privilège à la taille ou à la vitesse**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.FavorSizeOrSpeed%2A>.  
  
## Voir aussi  
 [\/O \(Optimiser le code\), options](../../build/reference/o-options-optimize-code.md)   
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)
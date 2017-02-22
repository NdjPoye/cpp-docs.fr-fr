---
title: "/Zl (Omettre le nom de la biblioth&#232;que par d&#233;faut) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/zi"
  - "VC.Project.VCCLCompilerTool.OmitDefaultLibName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Zl (option du compilateur C++)"
  - "bibliothèques par défaut, omettre les noms"
  - "omettre le nom de la bibliothèque par défaut (option du compilateur)"
  - "ZI (option du compilateur)"
  - "-Zl (option du compilateur C++)"
ms.assetid: b27d39d0-44d6-498c-84ae-27c1326fee59
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# /Zl (Omettre le nom de la biblioth&#232;que par d&#233;faut)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Omet le nom de la bibliothèque Runtime C par défaut du fichier .obj.  Par défaut, le compilateur place le nom de la bibliothèque dans le fichier .obj afin de diriger l'éditeur de liens vers la bibliothèque appropriée.  
  
## Syntaxe  
  
```  
/Zl  
```  
  
## Notes  
 Pour plus d'informations, consultez [Utiliser la bibliothèque runtime](../../build/reference/md-mt-ld-use-run-time-library.md).  
  
 Vous pouvez utiliser **\/Zl** pour compiler les fichiers .obj que vous envisagez de placer dans une bibliothèque.  Même si l'omission du nom de la bibliothèque ne permet d'économiser qu'une petite quantité d'espace pour un seul fichier .obj, le gain d'espace total économisé est important au niveau d'une bibliothèque qui contient de nombreux modules objet.  
  
 Il s'agit d'une option avancée.  La définition de cette option supprime la prise en charge de certaines bibliothèques Runtime C qui peuvent être nécessaires à votre application, ce qui entraîne des erreurs au moment de la liaison si votre application dépend de cette prise en charge.  Si vous utilisez cette option, vous devez fournir les composants requis d'une autre manière.  
  
 Utilisez [\/NODEFAULTLIB \(Ignorer les bibliothèques\)](../../build/reference/nodefaultlib-ignore-libraries.md). pour diriger l'éditeur de liens afin qu'il ignore les références de bibliothèque dans tous les fichiers .obj.  
  
 Pour plus d'informations, consultez [Fonctions de bibliothèque CRT](../../c-runtime-library/crt-library-features.md).  
  
 Lors de la compilation avec **\/Zl**, `_VC_NODEFAULTLIB` est défini.  Par exemple :  
  
```  
// vc_nodefaultlib.cpp  
// compile with: /Zl  
void Test() {  
   #ifdef _VC_NODEFAULTLIB  
      int i;  
   #endif  
  
   int i;   // C2086  
}  
```  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Cliquez sur le dossier **C\/C\+\+**.  
  
3.  Cliquez sur la page de propriétés **Avancé**.  
  
4.  Modifiez la propriété **Omettre les noms de bibliothèque par défaut**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OmitDefaultLibName%2A>.  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)
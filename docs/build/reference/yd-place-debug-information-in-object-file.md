---
title: "/Yd (Placer les informations de d&#233;bogage dans un fichier objet) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/yd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Yd (option du compilateur C++)"
  - "déboguer (C++), fichiers d'information de débogage"
  - "Yd (option du compilateur C++)"
  - "-Yd (option du compilateur C++)"
ms.assetid: c5a699fe-65ce-461e-964c-7f5eb2a8320a
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# /Yd (Placer les informations de d&#233;bogage dans un fichier objet)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Place des informations de débogage complètes dans tous les fichiers objets créés à partir d'un fichier d'en\-tête précompilé \(.pch\) si cette option est associée aux options [\/Yc](../../build/reference/yc-create-precompiled-header-file.md) et [\/Z7](../../build/reference/z7-zi-zi-debug-information-format.md).  Déconseillé.  
  
## Syntaxe  
  
```  
/Yd  
```  
  
## Notes  
 L'option **\/Yd** est déconseillée ; [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] prend désormais en charge plusieurs objets qui écrivent dans un fichier .pdb unique ; utilisez plutôt **\/Zi**.  Pour plus d'informations, consultez [Deprecated Compiler Options in Visual C\+\+ 2005](http://msdn.microsoft.com/fr-fr/aa59fce3-50b8-4f66-9aeb-ce09a7a84cce).  
  
 À moins que vous deviez distribuer une bibliothèque contenant des informations de débogage, utilisez l'option [\/Zi](../../build/reference/z7-zi-zi-debug-information-format.md) plutôt que **\/Z7** et **\/Yd**.  
  
 Le stockage d'informations de débogage complètes dans chaque fichier .obj est nécessaire uniquement pour la distribution de bibliothèques contenant des informations de débogage.  Il ralentit la compilation et demande beaucoup d'espace disque.  Quand les options **\/Yc** et **\/Z7** sont utilisées sans **\/Yd**, le compilateur stocke les informations de débogage communes dans le premier fichier .obj créé à partir du fichier .pch.  Le compilateur n'insère pas ces informations dans les autres fichiers .obj créés ensuite à partir du fichier .pch ; il insère à la place des références croisées aux informations.  Quel que soit le nombre de fichiers .obj qui utilisent le fichier .pch, un seul fichier .obj contient les informations de débogage communes.  
  
 Même si ce comportement par défaut se traduit par des délais de génération plus courts et une utilisation moindre de l'espace disque, il n'est pas souhaitable si une modification, même minime, requiert la régénération du fichier .obj contenant les informations de débogage communes.  Dans ce cas, le compilateur doit régénérer tous les fichiers .obj qui contiennent des références croisées au fichier .obj d'origine.  En outre, si un fichier .pch commun est utilisé par différents projets, il est difficile de garantir la fiabilité des références croisées à un seul fichier .obj.  
  
 Pour plus d'informations sur les en\-têtes précompilés, consultez :  
  
-   [\/Y \(En\-têtes précompilés\)](../../build/reference/y-precompiled-headers.md)  
  
-   [Création de fichiers d'en\-tête précompilés](../../build/reference/creating-precompiled-header-files.md)  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Cliquez sur le dossier **C\/C\+\+**.  
  
3.  Cliquez sur la page de propriétés **Ligne de commande**.  
  
4.  Spécifiez l'option du compilateur dans la zone **Options supplémentaires**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## Exemples  
 Prenons le cas de deux fichiers de base, F.cpp et G.cpp, chacun contenant ces instructions **\#include** :  
  
```  
#include "windows.h"  
#include "etc.h"  
```  
  
 La ligne de commande suivante crée le fichier d'en\-tête précompilé ETC.pch et le fichier objet F.obj :  
  
```  
CL /YcETC.H /Z7 F.CPP  
```  
  
 Le fichier objet F.obj comprend des informations sur les types et les symboles pour WINDOWS.h et ETC.h \(et tous les autres fichiers d'en\-tête qu'ils incluent\).  Vous pouvez à présent utiliser l'en\-tête précompilé ETC.pch pour compiler le fichier source G.cpp :  
  
```  
CL /YuETC.H /Z7 G.CPP  
```  
  
 Le fichier objet G.obj ne comprend pas les informations de débogage pour l'en\-tête précompilé, mais uniquement des références à ces informations figurant dans le fichier F.obj.  Notez que vous devez établir un lien avec le fichier F.obj.  
  
 Si votre en\-tête précompilé n'a pas été compilé avec **\/Z7**, vous pourrez l'utiliser dans des compilations ultérieures avec l'option **\/Z7**.  Cependant, les informations de débogage sont placées dans le fichier objet en cours, et les symboles locaux des fonctions et des types définis dans l'en\-tête précompilé ne seront pas disponibles pour le débogueur.  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)
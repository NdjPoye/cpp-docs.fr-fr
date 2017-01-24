---
title: "/hotpatch (Cr&#233;er une image corrigeable en m&#233;moire) | Microsoft Docs"
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
  - "/hotpatch"
  - "VC.Project.VCCLCompilerTool.CreateHotpatchableImage"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "correction en mémoire"
  - "-hotpatch (option du compilateur C++)"
  - "/hotpatch (option du compilateur C++)"
  - "correction en mémoire"
ms.assetid: aad539b6-c053-4c78-8682-853d98327798
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /hotpatch (Cr&#233;er une image corrigeable en m&#233;moire)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Prépare une image pour la création d'images corrigeables en mémoire.  
  
## Syntaxe  
  
```  
/hotpatch  
```  
  
## Notes  
 Lorsque **\/hotpatch** est utilisé dans une compilation, le compilateur vérifie que la première instruction de chaque fonction comprend au moins deux octets, ce qui est requis pour une correction en mémoire.  
  
 Pour terminer la préparation pour créer une image corrigeable en mémoire, après que vous ayez utilisé **\/hotpatch** pour compiler, vous devez utiliser [\/FUNCTIONPADMIN \(Création d'une image corrigeable en mémoire\)](../../build/reference/functionpadmin-create-hotpatchable-image.md) pour faire le lien.  Lorsque vous compilez et liez une image en utilisant un appel de cl.exe, **\/hotpatch** implique **\/functionpadmin**.  
  
 Comme Les instructions font toujours une taille d'au moins deux octets sur l'architecture ARM, et parce que la compilation x64 est toujours traitée comme si **\/hotpatch** a été spécifié, vous n'avez pas besoin de spécifier **\/hotpatch** lorsque vous compilez pour ces cibles ; Toutefois, vous devez encore faire le lien à l'aide de **\/functionpadmin** pour créer des images corrigeables en mémoire pour ces dernières.  L'option **\/hotpatch** du compilateur affecte uniquement la compilation x86.  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Sélectionnez le dossier **C\/C\+\+**.  
  
3.  Sélectionnez la page de propriétés **Ligne de commande**.  
  
4.  Ajoutez l'option du compilateur à la zone **Options supplémentaires**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## Conseils  
 Pour plus d'informations sur la gestion des mises à jour, consultez « aide de sécurité pour la gestion des mises à jour » à [http:\/\/www.microsoft.com\/technet\/security\/guidance\/PatchManagement.mspx](http://www.microsoft.com/technet/security/guidance/PatchManagement.mspx).  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)
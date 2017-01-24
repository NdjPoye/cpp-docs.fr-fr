---
title: "/ALLOWBIND (&#201;viter la liaison DLL) | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.PreventDLLBinding"
  - "/allowbind"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/ALLOWBIND (option de l'éditeur de liens)"
  - "ALLOWBIND (option de l'éditeur de liens)"
  - "-ALLOWBIND (option de l'éditeur de liens)"
  - "lier des DLL"
  - "DLL (C++), empêcher la liaison"
  - "éviter la liaison DLL"
ms.assetid: 30e37e24-12e4-407e-988a-39d357403598
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /ALLOWBIND (&#201;viter la liaison DLL)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/ALLOWBIND[:NO]  
```  
  
## Notes  
 \/ALLOWBIND:NO définit un bit dans l'en\-tête d'une DLL, qui indique à Bind.exe que l'image n'est pas autorisée à être liée.  Vous ne voulez peut\-être pas qu'une DLL soit liée si elle a été signée numériquement \(la liaison invalide la signature\).  
  
 Vous pouvez modifier une DLL existante pour la fonctionnalité \/ALLOWBIND à l'aide de l'option [\/ALLOWBIND](../../build/reference/allowbind.md) de l'utilitaire EDITBIN.  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, voir [Utilisation des propriétés de projet](../../ide/working-with-project-properties.md).  
  
2.  Développez **Propriétés de configuration** et **Éditeur de liens**, puis sélectionnez **Ligne de commande**.  
  
3.  Entrez `/ALLOWBIND:NO` dans **Options supplémentaires**.  
  
### Pour définir cette option de l'éditeur de liens par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)   
 [BindImage, fonction](http://msdn.microsoft.com/library/windows/desktop/ms679278.aspx)   
 [BindImageEx, fonction](http://msdn.microsoft.com/library/windows/desktop/ms679279.aspx)
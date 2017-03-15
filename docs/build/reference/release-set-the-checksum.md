---
title: "/RELEASE (D&#233;finir le total de Checksum) | Microsoft Docs"
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
  - "/release"
  - "VC.Project.VCLinkerTool.SetChecksum"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/RELEASE (option de l'éditeur de liens)"
  - "définition du checksum"
  - "RELEASE (option de l'éditeur de liens)"
  - "-RELEASE (option de l'éditeur de liens)"
ms.assetid: 93bcadf4-29ac-4824-914b-6997e3751d22
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /RELEASE (D&#233;finir le total de Checksum)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/RELEASE  
```  
  
## Notes  
 L'option \/RELEASE définit le checksum dans l'en\-tête d'un fichier .exe.  
  
 Le système d'exploitation a besoin de ce total de Checksum pour les pilotes de périphérique.  Il est recommandé de définir le total de Checksum pour les versions commercialisées des pilotes de périphérique afin de garantir la compatibilité avec les futurs systèmes d'exploitation.  
  
 L'option \/RELEASE est définie par défaut lorsque l'option [\/SUBSYSTEM:NATIVE](../../build/reference/subsystem-specify-subsystem.md) est spécifiée.  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Définition des propriétés de projets Visual C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le dossier **Éditeur de liens**.  
  
3.  Cliquez sur la page de propriétés **Avancé**.  
  
4.  Modifiez la propriété **Activation du Checksum**.  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SetChecksum%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)
---
title: "/SWAPRUN (Charger la sortie de l&#39;&#201;diteur de liens dans le fichier d&#39;&#233;change) | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.SwapRunFromNet"
  - "/swaprun"
  - "VC.Project.VCLinkerTool.SwapRunFromCD"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/SWAPRUN (option de l'éditeur de liens)"
  - "fichiers (C++), LINK"
  - "LINK (outil C++), sortie"
  - "éditeur de liens (C++), copier la sortie dans un fichier d'échange"
  - "fichiers de sortie, éditeur de liens"
  - "fichier d'échange pour la sortie de l'éditeur"
  - "SWAPRUN (option de l'éditeur de liens)"
  - "-SWAPRUN (option de l'éditeur de liens)"
ms.assetid: 4a1e7f46-4399-4161-8dfc-d6a71beaf683
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /SWAPRUN (Charger la sortie de l&#39;&#201;diteur de liens dans le fichier d&#39;&#233;change)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/SWAPRUN:{NET|CD}  
```  
  
## Notes  
 L'option \/SWAPRUN indique au système d'exploitation de copier d'abord la sortie de l'Éditeur de liens dans un fichier d'échange, puis d'exécuter l'image à partir de cet emplacement.  Il s'agit d'une fonctionnalité Windows NT 4.0 \(ou version ultérieure\).  
  
 Si NET est spécifié, le système d'exploitation copie d'abord l'image binaire du réseau dans un fichier d'échange, puis il la charge à partir de cet emplacement.  Cette option permet d'exécuter des applications sur le réseau.  Lorsqu'un CD\-ROM est spécifié, le système d'exploitation va copier l'image sur un disque amovible vers un fichier d'échange, puis le charger.  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Définition des propriétés de projets Visual C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le dossier **Éditeur de liens**.  
  
3.  Cliquez sur la page de propriétés **Système**.  
  
4.  Modifiez une des propriétés suivantes :  
  
    -   **Échange à partir du CD\-ROM**  
  
    -   **Échange à partir du réseau**  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
1.  Consultez les propriétés <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SwapRunFromCD%2A> et <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SwapRunFromNet%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)
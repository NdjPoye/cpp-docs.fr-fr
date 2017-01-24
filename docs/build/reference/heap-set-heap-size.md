---
title: "/HEAP (D&#233;finir la taille des tas) | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.HeapCommitSize"
  - "/heap"
  - "VC.Project.VCLinkerTool.HeapReserveSize"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/HEAP (option de l'éditeur de liens)"
  - "allocation des tas, définir la taille des tas"
  - "HEAP (option de l'éditeur de liens)"
  - "-HEAP (option de l'éditeur de liens)"
ms.assetid: a3f71927-7f1d-492c-9fdb-dfccb1a043da
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /HEAP (D&#233;finir la taille des tas)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/HEAP:reserve[,commit]  
```  
  
## Notes  
 L'option \/HEAP définit la taille des tas en octets.  Elle est valide uniquement lors de la génération d'un fichier .exe.  
  
 L'argument *reserve* spécifie la taille totale d'allocation du tas dans la mémoire virtuelle.  La taille par défaut du tas est de 1 Mo.  L'éditeur de liens arrondit la valeur spécifiée aux 4 octets les plus proches.  
  
 L'argument facultatif `commit` est soumis à l'interprétation du système d'exploitation.  Sous Windows NT et Windows 2000, il spécifie la quantité de mémoire physique à allouer dans chaque cas.  La mémoire virtuelle dédiée fait réserver de l'espace dans le fichier d'échange.  Une valeur de l'argument `commit` supérieure permet de gagner du temps quand l'application requiert davantage d'espace pour le tas, mais augmente les besoins en ressources mémoire et peut allonger la durée de la phase de démarrage.  
  
 Spécifiez les valeurs *reserve* et `commit` en notation décimale ou de langage C.  
  
 Cette fonctionnalité est également disponible via un fichier de définition de module avec l'option [HEAPSIZE](../../build/reference/heapsize.md).  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Définition des propriétés de projets Visual C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le dossier **Éditeur de liens**.  
  
3.  Cliquez sur la page de propriétés **Système**.  
  
4.  Modifiez la propriété **Taille de la validation des tas**.  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.HeapReserveSize%2A> et <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.HeapCommitSize%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)
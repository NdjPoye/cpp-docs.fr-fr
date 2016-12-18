---
title: "Classes wrapper | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "contrôles ActiveX (C++), classes wrapper"
  - "liaison de données (C++), contrôles ActiveX"
  - "classes wrapper (C++), contrôles ActiveX"
ms.assetid: ebbc17b9-cc1b-4c29-afa9-da7f9511876e
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classes wrapper
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Lorsque vous [insérez un contrôle](../../data/ado-rdo/inserting-the-control-into-a-visual-cpp-application.md) dans un projet Visual C\+\+, les classes wrapper du contrôle ne sont pas incluses par défaut.  Cependant, si vous souhaitez [modifier le comportement du contrôle](../../data/ado-rdo/modifying-a-control-s-run-time-behavior.md), vous pouvez écrire une classe wrapper pour ce contrôle.  Selon la façon dont vous envisagez de manipuler le contrôle par programme, vous devez écrire une ou plusieurs classes wrapper.  
  
 Une classe wrapper est disponible pour chacune des coclasses dans le fichier de bibliothèque de types \(.tlb\) du contrôle.  La classe wrapper du contrôle doit correspondre au nom du contrôle préfixé par la lettre C.  
  
 Pour plus d'informations sur le fonctionnement des classes wrapper, consultez le modèle objet pour la technologie de base du contrôle.  
  
 L'utilisation de [CWnd::GetDlgItem](../Topic/CWnd::GetDlgItem.md) requiert également des classes wrapper dans la mesure où la valeur de retour doit être convertie en classe de contrôle.  Par exemple :  
  
```  
CDBList* pDBList = 0;  
pDBList = static_cast<CDBList*>(GetDlgItem(IDC_DBLIST));  
```  
  
 En examinant le fichier .idl généré, vous pouvez déterminer les propriétés, les méthodes et les événements qui sont exposés par un contrôle, et découvrir aussi directement les déclarations des fonctions des accesseurs et des méthodes.  Vous pouvez obtenir des informations supplémentaires à partir du contrôle en utilisant l'[Explorateur d'objets OLE\/COM](../../data/ado-rdo/using-the-ole-com-object-viewer.md).  
  
## Voir aussi  
 [Utilisation des contrôles ActiveX](../../data/ado-rdo/using-activex-controls.md)   
 [Modification du comportement d'un contrôle au moment de l'exécution](../../data/ado-rdo/modifying-a-control-s-run-time-behavior.md)
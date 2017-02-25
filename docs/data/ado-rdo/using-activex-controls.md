---
title: "Utilisation des contr&#244;les ActiveX | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "contrôles ActiveX (C++), à propos des contrôles ActiveX"
  - "contrôles (C++), ActiveX"
ms.assetid: 33442173-205d-492f-82c8-9a8105358ec6
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Utilisation des contr&#244;les ActiveX
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les rubriques de cette section donnent une vue d'ensemble de l'utilisation des contrôles ActiveX.  
  
 Un contrôle ActiveX est un composant COM qui prend en charge des interfaces standard liées à la persistance, aux points de connexion et à l'hébergement.  Ces interfaces standard définissent un protocole qui permet à un contrôle d'être hébergé dans un conteneur de contrôle, d'échanger des messages et de gérer des événements.  
  
 À l'instar des serveurs COM, les contrôles ActiveX ont les caractéristiques suivantes :  
  
|Terme|Description|  
|-----------|-----------------|  
|Propriétés|Les contrôles possèdent des variables membres pour représenter leur état interne et sont implémentés en tant que fonctions d'accesseurs **Get** et `Set`.  Une fonction **Get** est générée pour chaque méthode d'accesseur au moyen d'une balise propget dans le fichier .idl.  Une fonction `Set` est générée pour chaque méthode d'accesseur au moyen d'une balise IDL propput ou propputref.<br /><br /> Utilisez des [Classes wrapper](../../data/ado-rdo/wrapper-classes.md) ou l'[Explorateur d'objets OLE\/COM](../../data/ado-rdo/using-the-ole-com-object-viewer.md) pour déterminer comment les fonctions d'accesseurs sont définies.|  
|Méthodes|Le comportement d'un contrôle est défini par ses méthodes publiques.  Les classes wrapper donnent accès aux méthodes d'un contrôle.<br /><br /> Si vous n'utilisez pas les classes wrapper \(option par défaut\), vous pouvez accéder aux méthodes d'un contrôle en obtenant un pointeur désignant une interface.<br /><br /> Un exemple de méthode publique est la méthode **Refresh** du contrôle de données ADO, qui met à jour le jeu de lignes récupéré.|  
|Événements|Un contrôle peut générer un événement afin de notifier à l'hôte que quelque chose s'est produit.  L'événement `OnClick` du contrôle Bouton en est un exemple.  Lorsque vous cliquez sur le bouton, celui\-ci génère un événement `OnClick`.  L'hôte du contrôle exécute alors le gestionnaire de cet événement, s'il en a un.|  
|Bibliothèque de types|Une bibliothèque de types indique à un conteneur de contrôle les propriétés, les méthodes et les événements pris en charge par un contrôle.  Les bibliothèques de types peuvent exister en tant que fichiers séparés \(avec une extension .tlb\) ou à l'intérieur du contrôle.<br /><br /> Les bibliothèques de types contiennent également des informations sur la coclasse du contrôle.  Une coclasse est une classe COM qui est identifiée à l'aide d'un GUID \(identificateur universel unique\).  Une coclasse contient une ou plusieurs interfaces définies par le contrôle.<br /><br /> Pour examiner les bibliothèques de types, utilisez l'[Explorateur d'objets OLE\/COM](../../data/ado-rdo/using-the-ole-com-object-viewer.md).|  
  
 Les rubriques suivantes décrivent l'utilisation d'un contrôle ActiveX :  
  
-   [Insertion du contrôle dans une application Visual C\+\+](../../data/ado-rdo/inserting-the-control-into-a-visual-cpp-application.md)  
  
-   [Classes wrapper](../../data/ado-rdo/wrapper-classes.md)  
  
-   [Création d'une connexion à une base de données](../../data/ado-rdo/creating-database-connections.md)  
  
-   [Définition des propriétés du contrôle au moment du design](../../data/ado-rdo/setting-control-properties-at-design-time.md)  
  
-   [Définition de gestionnaires d'événements pour les contrôles ActiveX](../../data/ado-rdo/setting-event-handlers-on-activex-controls.md)  
  
-   [Modification du comportement d'un contrôle au moment de l'exécution](../../data/ado-rdo/modifying-a-control-s-run-time-behavior.md)  
  
-   [Redistribution des contrôles](../../data/ado-rdo/redistributing-controls.md)  
  
## Voir aussi  
 [Contrôles liés aux données \(ADO et RDO\)](../../data/ado-rdo/data-bound-controls-ado-and-rdo.md)
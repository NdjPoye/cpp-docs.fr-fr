---
title: "Mod&#232;le d&#39;h&#233;bergement de contr&#244;les de donn&#233;es RDO (Remote Data Objects) dans un conteneur | Microsoft Docs"
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
  - "RemoteData (contrôle RDO), héberger un modèle"
  - "RemoteData (contrôle), héberger un modèle"
ms.assetid: ca598bac-9fef-40e6-b6cd-03d817e16b2e
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Mod&#232;le d&#39;h&#233;bergement de contr&#244;les de donn&#233;es RDO (Remote Data Objects) dans un conteneur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Un conteneur héberge un contrôle de données RDO \(Remote Data Objects\) de la manière suivante :  
  
-   Le conteneur obtient une interface IVBDSC à partir du contrôle de données.  S'il ne trouve pas IVBDSC, il ne s'agit alors pas d'un contrôle de données.  
  
-   Le conteneur obtient les interfaces **ICursor** à partir du contrôle de données.  Ces interfaces fournissent un objet Cursor pouvant être manipulé par un client.  
  
-   Le conteneur se raccorde à l'interface **INotifyDBEvents** du contrôle de données.  Cette interface permet au conteneur de recevoir des notifications émises par le contrôle de données.  Pour ce faire, le conteneur doit prendre en charge l'interface **INotifyDBEventsSink**.  
  
 Un conteneur héberge un contrôle lié aux données RDO de la manière suivante :  
  
-   Le contrôle prend en charge l'interface **IBoundObject** et le conteneur prend en charge l'interface **IBoundObjectSite**.  Le contrôle obtient l'interface **IBoundObjectSite** du conteneur, et le conteneur obtient l'interface **IBoundObject** à partir du contrôle.  
  
-   Le contrôle prend en charge l'interface **IPropNotifySink** et se raccorde au conteneur.  Le conteneur peut ainsi recevoir des notifications de la part du contrôle.  
  
-   Si le contrôle prend en charge **INotifyDBEventsSink**, il peut recevoir des notifications d'un contrôle de données RDO après s'être connecté à l'interface **INotifyDBEvents** du contrôle de données.  
  
-   Le contrôle peut recevoir des objets curseur en provenance du contrôle de données \(directement ou via le conteneur\).  Vous pouvez ensuite manipuler les curseurs et les faire défiler.  Le contrôle lié aux données RDO est alors lié avec succès.  
  
## Voir aussi  
 [Liaison de données RDO](../../data/ado-rdo/rdo-databinding.md)   
 [Utilisation de la liaison de données RDO dans Visual C\+\+](../../data/ado-rdo/using-rdo-databinding-in-visual-cpp.md)
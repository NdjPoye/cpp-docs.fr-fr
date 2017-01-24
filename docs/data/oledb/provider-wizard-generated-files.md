---
title: "Fichiers g&#233;n&#233;r&#233;s par l&#39;Assistant Fournisseur | Microsoft Docs"
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
  - "fournisseurs OLE DB, fichiers générés par l'Assistant"
ms.assetid: 6e1ac94b-eb90-4abf-82b3-06944b947ebc
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Fichiers g&#233;n&#233;r&#233;s par l&#39;Assistant Fournisseur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

L'Assistant Fournisseur OLE DB ATL génère les fichiers désignés ci\-après.  Les rubriques suivantes utilisent le nom court « MyProvider », mais les noms de fichiers exacts dépendent du choix que vous avez effectué lors de la création du fournisseur.  
  
|Nom du fichier|Description|  
|--------------------|-----------------|  
|MyProviderRS.cpp|Contient la méthode `Execute` de l'application d'assistance et le mappage de colonnes du fournisseur.|  
|MyProviderDS.h|Implémente l'objet data source.  Ce fichier d'en\-tête contient le mappage des propriétés pour les propriétés de la source de données.|  
|MyProviderRS.h|Implémente les objets commande et rowset.  Ce fichier d'en\-tête contient le mappage des propriétés pour les propriétés rowset et command.|  
|MyProviderSess.h|Implémente l'objet session.  Ce fichier d'en\-tête contient le mappage des propriétés pour les propriétés session.|  
|MyProvider.rgs|Contient les objets inscrits générés par l'Assistant Fournisseur OLE DB.|  
  
## Voir aussi  
 [Création d'un fournisseur OLE DB](../../data/oledb/creating-an-ole-db-provider.md)
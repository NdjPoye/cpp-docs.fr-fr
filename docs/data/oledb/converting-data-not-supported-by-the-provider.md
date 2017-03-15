---
title: "Conversion des donn&#233;es non&#160;prises en charge par le fournisseur | Microsoft Docs"
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
  - "modèles du fournisseur OLE DB, types de données non prises en charge"
ms.assetid: f495e50f-530a-4fab-ab54-e0c359785845
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Conversion des donn&#233;es non&#160;prises en charge par le fournisseur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Quand le consommateur demande un type de données qui n'est pas pris en charge par le fournisseur, le code du modèle du fournisseur OLE DB pour `IRowsetImpl::GetData` appelle Msdadc.dll pour convertir le type de données.  
  
 Si vous implémentez une interface comme `IRowsetChange` qui exige une conversion de données, vous pouvez appeler Msdaenum.dll pour effectuer la conversion.  Utilisez la fonction `GetData`, définie dans Atldb.h, comme un exemple.  
  
## Voir aussi  
 [Utilisation des modèles du fournisseur OLE DB](../../data/oledb/working-with-ole-db-provider-templates.md)
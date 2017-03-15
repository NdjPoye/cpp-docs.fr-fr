---
title: "Interfaces de l&#39;objet de commande | Microsoft Docs"
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
  - "interfaces de l'objet commande (C++)"
  - "objet commande (OLE DB)"
  - "OLE DB (C++), interfaces de l'objet commande"
ms.assetid: dacff5ae-252c-4f20-9ad7-4e602cc48536
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Interfaces de l&#39;objet de commande
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

L'objet de commande utilise l'interface `IAccessor` pour spécifier des liaisons de paramètre.  Le consommateur appelle `IAccessor::CreateAccessor`, en lui passant un tableau de structures `DBBINDING`.  `DBBINDING` contient des informations sur les liaisons de colonnes \(type et longueur, par exemple\).  Le fournisseur reçoit les structures et détermine comment les données doivent être transférées et si des conversions sont nécessaires.  
  
 L'interface `ICommandText` permet de spécifier une commande de texte.  L'interface `ICommandProperties` gère toutes les propriétés de commande.  
  
## Voir aussi  
 [Architecture des modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)
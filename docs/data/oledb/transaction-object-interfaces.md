---
title: "Interfaces de l&#39;objet transaction | Microsoft Docs"
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
  - "interfaces, liste de"
  - "interfaces, OLE DB"
  - "modèles du fournisseur OLE DB, interfaces d'objet"
  - "fournisseurs OLE DB, prise en charge des transactions"
  - "OLE DB, interfaces"
  - "interfaces d'objet de transaction"
ms.assetid: d2ce99ce-6f7a-4ff9-bc6e-acda3633d5c8
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Interfaces de l&#39;objet transaction
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

L'objet transaction définit une unité de travail atomique sur une source de données et détermine comment ces unités se rapportent les unes aux autres.  Cet objet n'est pas pris en charge directement par les modèles du fournisseur OLE DB \(autrement dit, vous devez créer votre propre objet\).  
  
 Le tableau suivant indique les interfaces obligatoires et facultatives définies par OLE DB pour un objet transaction.  
  
|Interface|Obligatoire ?|Implémentée par les modèles OLE DB ?|  
|---------------|-------------------|------------------------------------------|  
|[\<caps:sentence id\="tgt7" sentenceid\="63e99e63156fc90f114fa402662387ef" class\="tgtSentence"\>IConnectionPointContainer\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms683857)|Obligatoire|Non|  
|[\<caps:sentence id\="tgt10" sentenceid\="f5097e646bb93cceb560c38e13953a89" class\="tgtSentence"\>ITransaction\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/ms723053.aspx)|Obligatoire|Non|  
|[\<caps:sentence id\="tgt13" sentenceid\="130702210bcc45e1afd88b1f2aae1a0b" class\="tgtSentence"\>ISupportErrorInfo\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/ms715816.aspx)|Facultatif|Non|  
  
## Voir aussi  
 [Architecture des modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)
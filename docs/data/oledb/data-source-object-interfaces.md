---
title: "Interfaces de l&#39;objet source de donn&#233;es | Microsoft Docs"
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
  - "objets source de données (C++)"
  - "objets source de données (C++), interfaces"
  - "interfaces (C++), liste de"
  - "interfaces (C++), OLE DB"
  - "OLE DB (C++), interfaces"
  - "OLE DB (modèles du fournisseur) (C++), interfaces d'objet"
ms.assetid: 929e100c-c08c-4b64-8437-d8d1357226f6
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# Interfaces de l&#39;objet source de donn&#233;es
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Le tableau suivant indique les interfaces obligatoires et facultatives définies par OLE DB pour un objet data source.  
  
|Interface|Obligatoire ?|Implémentée par les modèles OLE DB ?|  
|---------------|-------------------|------------------------------------------|  
|`IDBCreateSession`|Obligatoire|Oui|  
|`IDBInitialize`|Obligatoire|Oui|  
|`IDBProperties`|Obligatoire|Oui|  
|[\<caps:sentence id\="tgt14" sentenceid\="731a3344bc1c6b5f8f54d9de3524f18a" class\="tgtSentence"\>IPersist\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms688695)|Obligatoire|Oui|  
|[\<caps:sentence id\="tgt17" sentenceid\="63e99e63156fc90f114fa402662387ef" class\="tgtSentence"\>IConnectionPointContainer\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms683857)|Facultatif|Non|  
|`IDBDataSourceAdmin`|Facultatif|Non|  
|`IDBInfo`|Facultatif|Non|  
|[\<caps:sentence id\="tgt26" sentenceid\="7e6a12ecd4cb3b1bd45dccf9421ed567" class\="tgtSentence"\>IPersistFile\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms687223)|Facultatif|Non|  
|`ISupportErrorInfo`|Facultatif|Non|  
  
 L'objet source de données implémente les interfaces `IDBProperties`, `IDBInitialize` et `IDBCreateSession` par héritage.  Vous pouvez choisir de prendre en charge des fonctionnalités supplémentaires en héritant ou non de l'une de ces classes d'implémentation.  Pour permettre la prise en charge de l'interface `IDBDataSourceAdmin`, l'héritage de la classe `IDBDataSourceAdminImpl` est nécessaire.  
  
## Voir aussi  
 [Architecture des modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)
---
title: "R&#233;cup&#233;ration d&#39;un BLOB | Microsoft Docs"
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
  - "objets binaires volumineux (BLOB), récupérer"
  - "OLE DB, objets binaires volumineux (BLOB)"
  - "récupérer des BLOB"
ms.assetid: 2893eb0a-5c05-4016-8914-1e40ccbaf0b3
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# R&#233;cup&#233;ration d&#39;un BLOB
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vous pouvez récupérer un objet de type BLOB \(Binary Large Object\) de diverses manières.  Vous pouvez utiliser **DBTYPE\_BYTES** pour récupérer le BLOB en tant que séquence d'octets, ou recourir à une interface de type `ISequentialStream`.  Pour plus d'informations, consultez [BLOBS et objets OLE](https://msdn.microsoft.com/en-us/library/ms711511.aspx) dans le Guide de référence du programmeur *OLE DB*.  
  
 Le code suivant montre comment récupérer un BLOB en utilisant `ISequentialStream`.  La macro [BLOB\_ENTRY](../../data/oledb/blob-entry.md) vous permet de spécifier l'interface et les indicateurs utilisés pour l'interface.  Après avoir ouvert la table, le code appelle **Read** à maintes reprises sur `ISequentialStream` pour lire les octets à partir du BLOB.  Le code appelle **Release** pour supprimer le pointeur de l'interface avant d'appeler `MoveNext` pour obtenir l'enregistrement suivant.  
  
```  
class CCategories  
{  
public:  
   ISequentialStream*   pPicture;  
  
BEGIN_COLUMN_MAP(CCategories)  
   BLOB_ENTRY(4, IID_ISequentialStream, STGM_READ, pPicture)  
END_COLUMN_MAP()  
};  
  
CTable<CAccessor<CCategories> > categories;  
ULONG          cb;  
BYTE            myBuffer[65536];  
  
categories.Open(session, "Categories");  
while (categories.MoveNext() == S_OK)  
{  
   do  
   {  
      categories.pPicture->Read(myBuffer, 65536, &cb);  
      // Do something with the buffer  
   } while (cb > 0);  
   categories.pPicture->Release();  
}  
```  
  
 Pour plus d'informations sur les macros qui gèrent les données BLOB, consultez « Macros de table de colonnes » dans [Macros et fonctions globales pour les modèles du consommateur OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md).  
  
## Voir aussi  
 [Utilisation des accesseurs](../../data/oledb/using-accessors.md)   
 [Macros et fonctions globales pour les modèles du consommateur OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)
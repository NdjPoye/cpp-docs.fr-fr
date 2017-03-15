---
title: "Utilisation d&#39;un recordset ADO existant | Microsoft Docs"
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
  - "ADO (recordsets C++)"
  - "OLE DB (modèles du consommateur), ADO (recordsets)"
  - "recordsets (C++), utiliser dans OLE DB"
ms.assetid: a9b1de8a-d379-49b1-a26e-578741e9f6a8
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Utilisation d&#39;un recordset ADO existant
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Pour combiner des modèles du consommateur OLE DB et ADO \(Active Data Objects\), utilisez ADO pour ouvrir un recordset \(correspondant à un jeu de lignes dans les modèles du consommateur OLE DB\).  Une fois que vous avez un recordset, connectez\-vous à un jeu de lignes OLE DB en procédant de la manière suivante :  
  
1.  Appelez `QueryInterface` pour les pointeurs `IRowset` et `IAccessor`.  
  
    ```  
    IRowset* lpRowset = NULL;  
    IAccessor* lpAccessor = NULL;  
    lpUnk->QueryInterface(IID_IRowset, (void**)&lpRowset);  
    lpUnk->QueryInterface(IID_IAccessor, (void**)&lpAccessor);  
    ```  
  
    > [!NOTE]
    >  *lpUnk* désigne l'objet **IUnknown** du recordset ADO.  
  
2.  Attachez l'accesseur et le jeu de lignes à leurs classes de modèles du consommateur OLE DB appropriées.  
  
    ```  
    CRowset rs;  
    CAccessor accessor;  
  
    accessor.AddAccessorInfo(0ul);      // 0 is the ordinal of an ADO accessor  
    rs.m_spRowset.Attach(lpRowset);      // use the Attach method of CComPtr<>  
    rs.SetAccessor(accessor);  
    ```  
  
## Voir aussi  
 [Utilisation des accesseurs](../../data/oledb/using-accessors.md)
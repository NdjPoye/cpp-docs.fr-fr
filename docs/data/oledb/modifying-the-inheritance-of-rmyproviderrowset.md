---
title: "Modification de l&#39;h&#233;ritage de RMyProviderRowset | Microsoft Docs"
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
  - "héritage (C++)"
  - "RMyProviderRowset"
ms.assetid: 33089c90-98a4-43e7-8e67-d4bb137e267e
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Modification de l&#39;h&#233;ritage de RMyProviderRowset
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Pour ajouter l'interface `IRowsetLocate` à l'exemple de fournisseur simple accessible en lecture seule, modifiez l'héritage de **RMyProviderRowset**.  Initialement, **RMyProviderRowset** hérite de `CRowsetImpl`.  Vous devez la modifier pour qu'elle hérite de **CRowsetBaseImpl**.  
  
 Pour ce faire, créez une nouvelle classe, `CMyRowsetImpl`, dans MyProviderRS.h :  
  
```  
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.h  
  
template <class T, class Storage, class CreatorClass, class ArrayType = CAtlArray<Storage> >  
class CMyRowsetImpl:  
   public CRowsetImpl<T, Storage, CreatorClass, ArrayType, CSimpleRow, IRowsetLocateImpl< T, IRowsetLocate > >  
{  
...  
};  
```  
  
 À présent, modifiez le mappage de l'interface COM dans MyProviderRS.h de façon à lui donner l'aspect suivant :  
  
```  
BEGIN_COM_MAP(CMyRowsetImpl)  
   COM_INTERFACE_ENTRY(IRowsetLocate)  
   COM_INTERFACE_ENTRY_CHAIN(_RowsetBaseClass)  
END_COM_MAP()  
```  
  
 Cette opération crée un mappage d'interface COM qui indique à `CMyRowsetImpl` d'appeler **QueryInterface** pour les deux interfaces `IRowset` et `IRowsetLocate`.  Pour assurer toute l'implémentation pour les autres classes rowset, le mappage lie la classe `CMyRowsetImpl` à la classe **CRowsetBaseImpl** définie par les modèles OLE DB ; le mappage utilise la macro COM\_INTERFACE\_ENTRY\_CHAIN, qui indique aux modèles OLE DB d'analyser le mappage COM dans **CRowsetBaseImpl** en réponse à un appel `QueryInterface`.  
  
 Enfin, liez `RAgentRowset` à `CMyRowsetBaseImpl` en modifiant `RAgentRowset` pour qu'elle hérite de `CMyRowsetImpl`, comme ceci :  
  
```  
class RAgentRowset : public CMyRowsetImpl<RAgentRowset, CAgentMan, CMyProviderCommand>  
```  
  
 `RAgentRowset` peut à présent utiliser l'interface `IRowsetLocate` tout en tirant parti du reste de l'implémentation pour la classe rowset.  
  
 Ensuite, vous pouvez [déterminer de manière dynamique les colonnes retournées au consommateur](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md).  
  
## Voir aussi  
 [Amélioration du fournisseur simple accessible en lecture seule](../../data/oledb/enhancing-the-simple-read-only-provider.md)
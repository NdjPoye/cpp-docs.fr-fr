---
title: AtlTraceErrorRecords | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.AtlTraceErrorRecords
- ATL::AtlTraceErrorRecords
- AtlTraceErrorRecords
dev_langs: C++
helpviewer_keywords: AtlTraceErrorRecords function
ms.assetid: b83970b3-dc2a-445c-9142-f52218719905
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4a3f8542f2c897f45916ac62fbac147259b2362d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="atltraceerrorrecords"></a>AtlTraceErrorRecords
Exporte les informations d’enregistrement de l’erreur OLE DB à l’unité de vidage si une erreur est retournée.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      inline void AtlTraceErrorRecords(   
   HRESULT hrErr = S_OK    
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `hErr`  
 [in] Un `HRESULT` retourné par une fonction membre de modèles du consommateur OLE DB.  
  
## <a name="remarks"></a>Notes  
 Si `hErr` n’est pas `S_OK`, `AtlTraceErrorRecords` exporte les informations de l’enregistrement d’erreur OLE DB à l’unité de vidage (le **déboguer** onglet de la fenêtre de sortie ou un fichier). Les informations de l’enregistrement d’erreur, qui sont obtenues à partir du fournisseur, incluent le numéro de ligne, la source, description, fichier d’aide, contexte et GUID pour chaque entrée enregistrement d’erreur. `AtlTraceErrorRecords`exporte ces informations uniquement dans les versions debug. Dans les versions release, il s’agit d’un stub vide qui est optimisé out.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [Macros et fonctions globales pour les modèles du consommateur OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [CDBErrorInfo, classe](../../data/oledb/cdberrorinfo-class.md)
---
title: CUtlProps::OnInterfaceRequested | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CUtlProps
dev_langs:
- C++
helpviewer_keywords:
- OnInterfaceRequested method
ms.assetid: a5e1a879-cff3-4e01-b902-2249a152984f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: cdac2b6069e5f72534a304794b65723bef8ceb47
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="cutlpropsoninterfacerequested"></a>CUtlProps::OnInterfaceRequested
Gère les demandes d’une interface facultative lorsqu’un consommateur appelle une méthode sur l’un de l’objet des interfaces de création.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
      virtual HRESULT CUtlPropsBase::OnInterfaceRequested(REFIID riid);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `riid`  
 [in] L’IID de l’interface demandée. Pour plus d’informations, consultez la description de la `riid` paramètre de `ICommand::Execute` dans les *de référence du programmeur OLE DB* (dans le *MDAC SDK*).  
  
## <a name="remarks"></a>Notes  
 **OnInterfaceRequested** gère les demandes de consommateur d’une interface facultative lorsqu’un consommateur appelle une méthode sur l’un de l’objet des interfaces de création (tel que **IDBCreateSession**, **IDBCreateCommand**, `IOpenRowset`, ou `ICommand`). Il définit la propriété OLE DB correspondante pour l’interface demandée. Par exemple, si le consommateur demande **IID_IRowsetLocate**, **OnInterfaceRequested** définit le **DBPROP_IRowsetLocate** interface. Cela tient à jour l’état approprié lors de la création de l’ensemble de lignes.  
  
 Cette méthode est appelée lorsque le consommateur appelle **IOpenRowset::OpenRowset** ou `ICommand::Execute`.  
  
 Si un consommateur ouvre un objet et demande une interface facultative, le fournisseur doit définir la propriété associée à cette interface pour `VARIANT_TRUE`. Pour permettre le traitement spécifique à la propriété, **OnInterfaceRequested** est appelée avant que le fournisseur **Execute** méthode est appelée. Par défaut, **OnInterfaceRequested** gère les interfaces suivantes :  
  
-   `IRowsetLocate`  
  
-   `IRowsetChange`  
  
-   `IRowsetUpdate`  
  
-   **IConnectionPointContainer**  
  
-   `IRowsetScroll`  
  
 Si vous souhaitez gérer d’autres interfaces, remplacez cette fonction dans votre classe de source, de session, de commande ou d’ensemble de lignes de données pour les fonctions de processus. Votre substitution doit passer par les interfaces de propriétés set/get normal pour vous assurer que définir des propriétés définit également des propriétés chaînées (consultez [OnPropertyChanged](../../data/oledb/cutlprops-onpropertychanged.md)).  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldb.h  
  
## <a name="see-also"></a>Voir aussi  
 [CUtlProps, classe](../../data/oledb/cutlprops-class.md)
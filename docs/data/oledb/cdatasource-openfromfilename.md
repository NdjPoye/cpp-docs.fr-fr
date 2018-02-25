---
title: CDataSource::OpenFromFileName | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDataSource::OpenFromFileName
- ATL::CDataSource::OpenFromFileName
- OpenFromFileName
- CDataSource.OpenFromFileName
- ATL.CDataSource.OpenFromFileName
dev_langs:
- C++
helpviewer_keywords:
- OpenFromFileName method
ms.assetid: c4226de6-59da-4368-9c15-c5afab86f68b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a5ff7df5d0490910a7198fa8a1f2560b98a8570d
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="cdatasourceopenfromfilename"></a>CDataSource::OpenFromFileName
Ouvre une source de données à partir d'un fichier spécifié par le nom de fichier fourni par l'utilisateur.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT OpenFromFileName(LPCOLESTR szFileName) throw();  
```  
  
#### <a name="parameters"></a>Paramètres  
 `szFileName`  
 [in] Nom d'un fichier, généralement un fichier de connexion de source de données au format .UDL.  
  
 Pour plus d’informations sur les fichiers de liaison de données (fichiers .udl), consultez [Data Link API Overview](https://msdn.microsoft.com/en-us/library/ms718102.aspx) dans le Kit de développement logiciel Windows.  
  
## <a name="return-value"></a>Valeur de retour  
 `HRESULT` standard.  
  
## <a name="remarks"></a>Notes  
 Cette méthode ouvre un objet source de données à l’aide des composants de service d’oledb32.dll ; cette DLL contient l’implémentation des fonctionnalités Composants de service, telles que la mise en pool de ressources, l’inscription de transaction automatique, etc. Pour plus d’informations, consultez « Services OLE DB » dans la référence du programmeur OLE DB à l’adresse [http://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true](http://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true).  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CDataSource, classe](../../data/oledb/cdatasource-class.md)
---
title: CDataSource::OpenWithPromptFileName | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDataSource.OpenWithPromptFileName
- OpenWithPromptFileName
- ATL::CDataSource::OpenWithPromptFileName
- ATL.CDataSource.OpenWithPromptFileName
- CDataSource::OpenWithPromptFileName
dev_langs: C++
helpviewer_keywords: OpenWithPromptFileName method
ms.assetid: 89460504-1aaf-4412-aa7b-fa5a4b39ada3
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 776ad6e52c93947c5b6a5c4a3e2b4d0266d98154
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="cdatasourceopenwithpromptfilename"></a>CDataSource::OpenWithPromptFileName
Cette méthode présente une invite à l'utilisateur sous la forme d'une boîte de dialogue, puis ouvre une source de données correspondant au fichier spécifié par l'utilisateur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      HRESULT OpenWithPromptFileName(   
   HWND hWnd = GetActiveWindow(   
   ),   
   DBPROMPTOPTIONS dwPromptOptions = DBPROMPTOPTIONS_NONE,   
   LPCOLESTR szInitialDirectory = NULL    
) throw( );  
```  
  
#### <a name="parameters"></a>Paramètres  
 `hWnd`  
 [in] Handle de fenêtre devant être le parent de la boîte de dialogue.  
  
 `dwPromptOptions`  
 [in] Détermine le style de la boîte de dialogue de recherche à afficher. Consultez Msdasc.h pour connaître les valeurs possibles.  
  
 *szInitialDirectory*  
 [in] Répertoire initial à afficher dans la boîte de dialogue de recherche.  
  
## <a name="return-value"></a>Valeur de retour  
 `HRESULT` standard.  
  
## <a name="remarks"></a>Remarques  
 Cette méthode ouvre un objet source de données à l’aide des composants de service d’oledb32.dll ; cette DLL contient l’implémentation des fonctionnalités Composants de service, telles que la mise en pool de ressources, l’inscription de transaction automatique, etc. Pour plus d’informations, consultez « Services OLE DB » dans la référence du programmeur OLE DB à l’adresse [http://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true](http://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true).  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CDataSource, classe](../../data/oledb/cdatasource-class.md)
---
title: CDataSource::OpenFromInitializationString | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDataSource.OpenFromInitializationString
- OpenFromInitializationString
- CDataSource::OpenFromInitializationString
- ATL::CDataSource::OpenFromInitializationString
- ATL.CDataSource.OpenFromInitializationString
dev_langs: C++
helpviewer_keywords: OpenFromInitializationString method
ms.assetid: 5ef1f1fd-92a9-4e1c-ad80-d3601b094b8c
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 294c5cd893b04dd477a002adb6dc03fa33c60a29
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="cdatasourceopenfrominitializationstring"></a>CDataSource::OpenFromInitializationString
Ouvre une source de données spécifiée par la chaîne fournie par l’utilisateur de l’initialisation.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      HRESULT OpenFromInitializationString(   
   LPCOLESTR szInitializationString,   
   bool fPromptForInfo = false    
) throw( );  
```  
  
#### <a name="parameters"></a>Paramètres  
 *szInitializationString*  
 [in] La chaîne d’initialisation.  
  
 *fPromptForInfo*  
 [in] Si cet argument a la valeur **true**, puis `OpenFromInitializationString` définira la **DBPROP_INIT_PROMPT** propriété **DBPROMPT_COMPLETEREQUIRED**, ce qui indique que l’utilisateur doit être vous y êtes invité uniquement si plus d’informations est nécessaire. Cela est utile dans les situations dans lesquelles la chaîne d’initialisation spécifie une base de données requiert un mot de passe, mais la chaîne ne contient pas le mot de passe. L’utilisateur sera invité pour un mot de passe (ou toutes les informations manquantes) lorsque vous tentez de vous connecter à la base de données.  
  
 La valeur par défaut est **false**, ce qui indique que l’utilisateur invité jamais (définit **DBPROP_INIT_PROMPT** à **DBPROMPT_NOPROMPT**).  
  
## <a name="return-value"></a>Valeur de retour  
 `HRESULT` standard.  
  
## <a name="remarks"></a>Notes  
 Cette méthode ouvre un objet source de données à l’aide des composants de service d’oledb32.dll ; cette DLL contient l’implémentation des fonctionnalités Composants de service, telles que la mise en pool de ressources, l’inscription de transaction automatique, etc.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CDataSource, classe](../../data/oledb/cdatasource-class.md)
---
title: CDynamicParameterAccessor::GetParamString | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDynamicParameterAccessor.GetParamString
- GetParamString
- CDynamicParameterAccessor::GetParamString
- ATL.CDynamicParameterAccessor.GetParamString
- ATL::CDynamicParameterAccessor::GetParamString
dev_langs: C++
helpviewer_keywords: GetParamString method
ms.assetid: 078c2b1c-7072-47c1-a203-f47e75363f91
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ed04d3258ad5f4d5ed68a32b32923432577453ba
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="cdynamicparameteraccessorgetparamstring"></a>CDynamicParameterAccessor::GetParamString
Récupère les données de chaîne du paramètre spécifié stocké en mémoire tampon.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      bool GetParamString(  
   DBORDINAL nParam,  
   CSimpleStringA& strOutput  
) throw( );  
bool GetParamString(  
   DBORDINAL nParam,  
   CSimpleStringW& strOutput  
) throw( );  
bool GetParamString(  
   DBORDINAL nParam,  
   CHAR* pBuffer,  
   size_t* pMaxLen  
) throw( );  
bool GetParamString(  
   DBORDINAL nParam,  
   WCHAR* pBuffer,  
   size_t* pMaxLen  
) throw( );  
```  
  
#### <a name="parameters"></a>Paramètres  
 `nParam`  
 [in] Le numéro de paramètre (offset à partir de 1). Le paramètre 0 est réservé pour les valeurs de retournés. Le paramètre est l’index du paramètre en fonction de son ordre dans le SQL ou d’un appel de procédure stockée. Consultez [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) pour obtenir un exemple.  
  
 `strOutput`  
 [out] L’ANSI (**CSimpleStringA**) ou Unicode (**CSimpleStringW**) chaîne de données du paramètre spécifié. Vous devez passer un paramètre de type `CString`, par exemple :  
  
 [!code-cpp[NVC_OLEDB_Consumer#9](../../data/oledb/codesnippet/cpp/cdynamicparameteraccessor-getparamstring_1.cpp)]  
  
 `pBuffer`  
 [out] Un pointeur vers l’ANSI (**CHAR**) ou Unicode (**WCHAR**) chaîne de données du paramètre spécifié.  
  
 `pMaxLen`  
 [out] Un pointeur vers la taille de la mémoire tampon pointée par `pBuffer` (en caractères, y compris le caractère NULL de fin).  
  
## <a name="remarks"></a>Notes  
 Retourne **true** en cas de réussite ou **false** en cas d’échec.  
  
 Si `pBuffer` est NULL, cette méthode définit la taille de la mémoire tampon requise dans la mémoire vers laquelle pointée `pMaxLen` et retourner **true** sans copier les données.  
  
 Cette méthode échoue si la mémoire tampon `pBuffer` n’est pas suffisamment grande pour contenir la chaîne entière.  
  
 Utilisez `GetParamString` pour récupérer les données de paramètre de chaîne à partir de la mémoire tampon. Utilisez [GetParam](../../data/oledb/cdynamicparameteraccessor-getparam.md) pour récupérer des données de paramètre de chaîne à partir de la mémoire tampon.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CDynamicParameterAccessor, classe](../../data/oledb/cdynamicparameteraccessor-class.md)
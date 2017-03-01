---
title: "Macros d’échange de données de Registre | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- RegistryDataExchange function, macros
ms.assetid: c1bc5e79-2307-43d2-9d10-3a62ffadf473
caps.latest.revision: 16
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: ee3c1d639ee4a6c6bd6cf26a8c59bb1a37a4fa02
ms.lasthandoff: 02/24/2017

---
# <a name="registry-data-exchange-macros"></a>Registre des Macros de données Exchange
Ces macros effectuent des opérations d’échange de données de Registre.  
  
|||  
|-|-|  
|[BEGIN_RDX_MAP](#begin_rdx_map)|Marque le début de la carte de l’échange de données de Registre.|  
|[END_RDX_MAP](#end_rdx_map)|Marque la fin de la carte de l’échange de données de Registre.|  
|[RDX_BINARY](#rdx_binary)|Associe l’entrée de Registre spécifiée à une variable de membre spécifié de type BYTE.|  
|[RDX_CSTRING_TEXT](#rdx_cstring_text)|Associe l’entrée de Registre spécifiée à une variable de membre spécifié du type CString.|  
|[RDX_DWORD](#rdx_dword)|Associe l’entrée de Registre spécifiée à une variable de membre spécifié de type DWORD.|  
|[RDX_TEXT](#rdx_text)|Associe l’entrée de Registre spécifiée à une variable de membre spécifié de type TCHAR.|  

## <a name="requirements"></a>Spécifications  
 **En-tête :** atlplus.h  
   
##  <a name="a-namebeginrdxmapa--beginrdxmap"></a><a name="begin_rdx_map"></a>BEGIN_RDX_MAP  
 Marque le début de la carte de l’échange de données de Registre.  
  
```
BEGIN_RDX_MAP
```  
  
### <a name="remarks"></a>Remarques  
 Les macros suivantes sont utilisées dans l’Explorateur de l’échange de données de Registre pour lire et écrire des entrées dans le Registre système :  
  
|Macro|Description|  
|-----------|-----------------|  
|[RDX_BINARY](#rdx_binary)|Associe l’entrée de Registre spécifiée à une variable de membre spécifié de type BYTE.|  
|[RDX_DWORD](#rdx_dword)|Associe l’entrée de Registre spécifiée à une variable de membre spécifié de type DWORD.|  
|[RDX_CSTRING_TEXT](#rdx_cstring_text)|Associe l’entrée de Registre spécifiée à une variable de membre spécifié du type CString.|  
|[RDX_TEXT](#rdx_text)|Associe l’entrée de Registre spécifiée à une variable de membre spécifié de type TCHAR.|  
  
 La fonction globale [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), ou la fonction membre du même nom créé par le `BEGIN_RDX_MAP` et `END_RDX_MAP` macros, doit être utilisé chaque fois que votre code a besoin d’échanger des données entre le Registre système et les variables spécifiées dans le mappage RDX.  
  
##  <a name="a-nameendrdxmapa--endrdxmap"></a><a name="end_rdx_map"></a>END_RDX_MAP  
 Marque la fin de la carte de l’échange de données de Registre.  
  
```
END_RDX_MAP
```  
  
##  <a name="a-namerdxbinarya--rdxbinary"></a><a name="rdx_binary"></a>RDX_BINARY  
 Associe l’entrée de Registre spécifiée à une variable de membre spécifié de type BYTE.  
  
```
RDX_BINARY(
    rootkey, 
    subkey, 
    valuename, 
    member, 
    member_size )
```  
  
### <a name="parameters"></a>Paramètres  
 `rootkey`  
 La clé racine du Registre.  
  
 `subkey`  
 La sous-clé de Registre.  
  
 `valuename`  
 La clé de Registre.  
  
 `member`  
 La variable membre à associer à l’entrée de Registre spécifié.  
  
 `member_size`  
 La taille, en octets, de la variable membre.  
  
### <a name="remarks"></a>Remarques  
 Cette macro est utilisée conjointement avec la `BEGIN_RDX_MAP` et `END_RDX_MAP` macros pour associer une variable membre à une entrée de Registre donné. La fonction globale [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), ou la fonction membre du même nom créé par le `BEGIN_RDX_MAP` et `END_RDX_MAP` macros, doit servir à effectuer l’échange de données entre le Registre système et les variables de membre dans la carte RDX.  
  
##  <a name="a-namerdxcstringtexta--rdxcstringtext"></a><a name="rdx_cstring_text"></a>RDX_CSTRING_TEXT  
 Associe l’entrée de Registre spécifiée à une variable de membre spécifié du type CString.  
  
```
RDX_CSTRING_TEXT(
    rootkey, 
    subkey, 
    valuename, 
    member, 
    member_size )
```  
  
### <a name="parameters"></a>Paramètres  
 `rootkey`  
 La clé racine du Registre.  
  
 `subkey`  
 La sous-clé de Registre.  
  
 `valuename`  
 La clé de Registre.  
  
 `member`  
 La variable membre à associer à l’entrée de Registre spécifié.  
  
 `member_size`  
 La taille, en octets, de la variable membre.  
  
### <a name="remarks"></a>Notes  
 Cette macro est utilisée conjointement avec la `BEGIN_RDX_MAP` et `END_RDX_MAP` macros pour associer une variable membre à une entrée de Registre donné. La fonction globale [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), ou la fonction membre du même nom créé par le `BEGIN_RDX_MAP` et `END_RDX_MAP` macros, doit servir à effectuer l’échange de données entre le Registre système et les variables de membre dans la carte RDX.  
  
##  <a name="a-namerdxdworda--rdxdword"></a><a name="rdx_dword"></a>RDX_DWORD  
 Associe l’entrée de Registre spécifiée à une variable de membre spécifié de type DWORD.  
  
```
RDX_DWORD(
    rootkey, 
    subkey, 
    valuename, 
    member, 
    member_size )
```  
  
### <a name="parameters"></a>Paramètres  
 `rootkey`  
 La clé racine du Registre.  
  
 `subkey`  
 La sous-clé de Registre.  
  
 `valuename`  
 La clé de Registre.  
  
 `member`  
 La variable membre à associer à l’entrée de Registre spécifié.  
  
 `member_size`  
 La taille, en octets, de la variable membre.  
  
### <a name="remarks"></a>Remarques  
 Cette macro est utilisée conjointement avec la `BEGIN_RDX_MAP` et `END_RDX_MAP` macros pour associer une variable membre à une entrée de Registre donné. La fonction globale [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), ou la fonction membre du même nom créé par le `BEGIN_RDX_MAP` et `END_RDX_MAP` macros, doit servir à effectuer l’échange de données entre le Registre système et les variables de membre dans la carte RDX.  
  
##  <a name="a-namerdxtexta--rdxtext"></a><a name="rdx_text"></a>RDX_TEXT  
 Associe l’entrée de Registre spécifiée à une variable de membre spécifié de type TCHAR.  
  
```
RDX_TEXT(
    rootkey, 
    subkey, 
    valuename, 
    member, 
    member_size )
```  
  
### <a name="parameters"></a>Paramètres  
 `rootkey`  
 La clé racine du Registre.  
  
 `subkey`  
 La sous-clé de Registre.  
  
 `valuename`  
 La clé de Registre.  
  
 `member`  
 La variable membre à associer à l’entrée de Registre spécifié.  
  
 `member_size`  
 La taille, en octets, de la variable membre.  
  
### <a name="remarks"></a>Notes  
 Cette macro est utilisée conjointement avec la `BEGIN_RDX_MAP` et `END_RDX_MAP` macros pour associer une variable membre à une entrée de Registre donné. La fonction globale [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange), ou la fonction membre du même nom créé par le `BEGIN_RDX_MAP` et `END_RDX_MAP` macros, doit servir à effectuer l’échange de données entre le Registre système et les variables de membre dans la carte RDX.  
  
## <a name="see-also"></a>Voir aussi  
 [Macros](../../atl/reference/atl-macros.md)   
 [RegistryDataExchange](../../atl/reference/registry-and-typelib-global-functions.md#registrydataexchange)









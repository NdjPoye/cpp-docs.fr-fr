---
title: Classe de _U_MENUorID | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL._U_MENUorID
- ATL::_U_MENUorID
- _U_MENUorID
dev_langs:
- C++
helpviewer_keywords:
- U_MENUorID class
- _U_MENUorID class
ms.assetid: cfc8032b-61b4-4a68-ba3a-92b82500ccae
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: f7c0a5c34c4e103f830a029f58cdfa00dcb58a32
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="umenuorid-class"></a>_U_MENUorID (classe)
Cette classe fournit des wrappers pour **CreateWindow** et **CreateWindowEx**.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peut pas être utilisées dans les applications qui s’exécutent dans le Windows Runtime.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class _U_MENUorID
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[_U_MENUorID::_U_MENUorID](#_u_menuorid___u_menuorid)|Constructeur.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[_U_MENUorID::m_hMenu](#_u_menuorid__m_hmenu)|Handle d’un menu.|  
  
## <a name="remarks"></a>Remarques  
 Cette classe d’argument d’adaptateur permet à l’ID ( **UINT**s) ou des handles de menu ( `HMENU`s) doivent être passés à une fonction sans nécessiter une conversion explicite de la part de l’appelant.  
  
 Cette classe est conçue pour l’implémentation des wrappers pour l’API Windows, en particulier le [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) et [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) les fonctions qui acceptent un `HMENU` argument peut être un identificateur de fenêtre enfant ( **UINT**) au lieu d’un handle de menu. Par exemple, vous pouvez voir cette classe en cours d’utilisation en tant que paramètre [CWindowImpl::Create](cwindowimpl-class.md#create).  

  
 La classe définit deux surcharges de constructeur : une accepte un **UINT** argument et l’autre accepte un `HMENU` argument. Le **UINT** argument est simplement converti vers un `HMENU` dans le constructeur et le résultat stocké dans le membre de données de la classe, [m_hMenu](#_u_menuorid__m_hmenu). L’argument de la `HMENU` constructeur est stocké directement, sans conversion.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlwin.h  
  
##  <a name="_u_menuorid__m_hmenu"></a>_U_MENUorID::m_hMenu  
 La classe contient la valeur passée à un de ses constructeurs comme un public `HMENU` membre de données.  
  
```
HMENU m_hMenu;
```  
  
##  <a name="_u_menuorid___u_menuorid"></a>_U_MENUorID::_U_MENUorID  
 Le **UINT** argument est simplement converti vers un `HMENU` dans le constructeur et le résultat stocké dans le membre de données de la classe, [m_hMenu](#_u_menuorid__m_hmenu).  
  
```
_U_MENUorID(UINT nID);  
_U_MENUorID(HMENU hMenu);
```  
  
### <a name="parameters"></a>Paramètres  
 `nID`  
 Un identificateur de fenêtre enfant.  
  
 `hMenu`  
 Un descripteur de menu.  
  
### <a name="remarks"></a>Remarques  
 L’argument de la `HMENU` constructeur est stocké directement, sans conversion.  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)


---
title: Interface de IAxWinAmbientDispatchEx | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IAxWinAmbientDispatchEx
- No header/ATL::IAxWinAmbientDispatchEx
- No header/ATL::SetAmbientDispatch
dev_langs: C++
helpviewer_keywords: IAxWinAmbientDispatchEx interface
ms.assetid: 2c25e079-6128-4278-bc72-b2c6195ba7ef
caps.latest.revision: "25"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 92eed1ce48c4aed1ae535b4ae3751501c432281d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="iaxwinambientdispatchex-interface"></a>Interface de IAxWinAmbientDispatchEx
Cette interface implémente des propriétés ambiantes supplémentaires pour un contrôle hébergé.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peut pas être utilisées dans les applications qui s’exécutent dans le Windows Runtime.  
  
## <a name="syntax"></a>Syntaxe  
  
```
MIDL_INTERFACE("B2D0778B - AC99 - 4c58 - A5C8 - E7724E5316B5") IAxWinAmbientDispatchEx : public IAxWinAmbientDispatch
```  
  
## <a name="members"></a>Membres  
  
### <a name="methods"></a>Méthodes  
  
|||  
|-|-|  
|[SetAmbientDispatch](#setambientdispatch)|Cette méthode est appelée pour compléter l’interface de la propriété ambiante par défaut avec une interface définie par l’utilisateur.|  
  
## <a name="remarks"></a>Remarques  
 Inclure cette interface dans les applications ATL qui sont liées statiquement à ATL et hôte des contrôles ActiveX, notamment les contrôles ActiveX qui ont des propriétés ambiantes. Non compris cette interface génère cette assertion : « Vous avez oublié passer le LIBID à CComModule::Init »  
  
 Cette interface est exposée par le contrôle ActiveX de d’ATL qui héberge les objets. Dérivée de [IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md), `IAxWinAmbientDispatchEx` ajoute une méthode qui vous permet de compléter l’interface de propriété ambiante fournie par ATL avec celle de votre choix.  
  
 [AXHost](https://msdn.microsoft.com/library/system.windows.forms.axhost.aspx) essaie de charger les informations de type sur `IAxWinAmbientDispatch` et `IAxWinAmbientDispatchEx` à partir de la bibliothèque de types qui contient le code.  
  
 Si vous établissez la liaison ATL90.dll, **AXHost** charge les informations de type à partir de la bibliothèque de types dans la DLL.  
  
 Consultez [hébergement ActiveX des contrôles à l’aide de ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) pour plus d’informations.  
  
## <a name="requirements"></a>Spécifications  
 La définition de cette interface est disponible dans plusieurs formes, comme indiqué dans le tableau suivant.  
  
|Type de définition|Fichier|  
|---------------------|----------|  
|IDL|atliface.idl|  
|Bibliothèque de types|ATL.dll|  
|C++|atliface.h (également inclus dans ATLBase.h)|  
  
##  <a name="setambientdispatch"></a>IAxWinAmbientDispatchEx::SetAmbientDispatch  
 Cette méthode est appelée pour compléter l’interface de la propriété ambiante par défaut avec une interface définie par l’utilisateur.  
  
```
virtual HRESULT STDMETHODCALLTYPE SetAmbientDispatch(IDispatch* pDispatch) = 0;
```  
  
### <a name="parameters"></a>Paramètres  
 *pDispatch*  
 Pointeur vers la nouvelle interface.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Lorsque `SetAmbientDispatch` est appelée avec un pointeur vers une nouvelle interface, cette nouvelle interface servira à appeler des propriétés ou les méthodes demandées par le contrôle hébergé, si ces propriétés ne sont pas déjà fournies par [IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md).  
  
## <a name="see-also"></a>Voir aussi  
 [IAxWinAmbientDispatch, interface](../../atl/reference/iaxwinambientdispatch-interface.md)

---
title: Classe de CComObjectStack | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CComObjectStack
- ATL.CComObjectStack
- ATL::CComObjectStack<Base>
- ATL.CComObjectStack<Base>
- CComObjectStack
dev_langs:
- C++
helpviewer_keywords:
- CComObjectStack class
ms.assetid: 3da72c40-c834-45f6-bb76-6ac204028d80
caps.latest.revision: 19
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
ms.openlocfilehash: 0738eae13fdca5906596194016ce22812fbfcd36
ms.lasthandoff: 02/24/2017

---
# <a name="ccomobjectstack-class"></a>CComObjectStack (classe)
Cette classe crée un objet COM temporaire et lui fournit une implémentation squelette de **IUnknown**.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class  Base>  
class CComObjectStack
 : public Base
```  
  
#### <a name="parameters"></a>Paramètres  
 `Base`  
 Votre classe, dérivée de [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) ou [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), ainsi que toute autre interface souhaitées prendre en charge sur l’objet.  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CComObjectStack::CComObjectStack](#ccomobjectstack)|Constructeur.|  
|[CComObjectStack :: ~ CComObjectStack](#dtor)|Destructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CComObjectStack::AddRef](#addref)|Retourne zéro. En mode débogage, appelle `_ASSERTE`.|  
|[CComObjectStack::QueryInterface](#queryinterface)|Retourne **E_NOINTERFACE**. En mode débogage, appelle `_ASSERTE`.|  
|[CComObjectStack::Release](#release)|Retourne zéro. En mode débogage, appelle `_ASSERTE`. ~|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CComObjectStack::m_hResFinalConstruct](#m_hresfinalconstruct)|Contient le **HRESULT** retournée lors de la construction de la `CComObjectStack` objet.|  
  
## <a name="remarks"></a>Remarques  
 `CComObjectStack`est utilisé pour créer un objet COM temporaire et fournir l’objet une implémentation squelette de **IUnknown**. En règle générale, l’objet est utilisé comme une variable locale dans une fonction (qui est, placée sur la pile). Étant donné que l’objet est détruit à la fonction se termine, le décompte de références n’est pas effectuée pour accroître l’efficacité.  
  
 L’exemple suivant montre comment créer un objet COM utilisé dans une fonction :  
  
 [!code-cpp[NVC_ATL_COM&#42;](../../atl/codesnippet/cpp/ccomobjectstack-class_1.cpp)]  
  
 L’objet temporaire `Tempobj` est placé sur la pile et disparaît automatiquement lorsque la fonction se termine.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `Base`  
  
 `CComObjectStack`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlcom.h  
  
##  <a name="a-nameaddrefa--ccomobjectstackaddref"></a><a name="addref"></a>CComObjectStack::AddRef  
 Retourne zéro.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne zéro.  
  
### <a name="remarks"></a>Notes  
 En mode débogage, appelle `_ASSERTE`.  
  
##  <a name="a-nameccomobjectstacka--ccomobjectstackccomobjectstack"></a><a name="ccomobjectstack"></a>CComObjectStack::CComObjectStack  
 Constructeur.  
  
```
CComObjectStack(void* = NULL);
```  
  
### <a name="remarks"></a>Remarques  
 Appels `FinalConstruct` et définit ensuite [m_hResFinalConstruct](#m_hresfinalconstruct) à la `HRESULT` retourné par `FinalConstruct`. Si vous n’avez pas dérivé votre classe de base à partir de [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md), vous devez fournir vos propres `FinalConstruct` méthode. Le destructeur appelle `FinalRelease`.  
  
##  <a name="a-namedtora--ccomobjectstackccomobjectstack"></a><a name="dtor"></a>CComObjectStack :: ~ CComObjectStack  
 Destructeur.  
  
```
CComObjectStack();
```  
  
### <a name="remarks"></a>Notes  
 Libère toutes les ressources attribuées et les appels [FinalRelease](ccomobjectrootex-class.md#finalrelease).  
  
##  <a name="a-namemhresfinalconstructa--ccomobjectstackmhresfinalconstruct"></a><a name="m_hresfinalconstruct"></a>CComObjectStack::m_hResFinalConstruct  
 Contient le `HRESULT` retourné en appelant `FinalConstruct` pendant la construction de la `CComObjectStack` objet.  
  
```
HRESULT    m_hResFinalConstruct;
```  
  
##  <a name="a-namequeryinterfacea--ccomobjectstackqueryinterface"></a><a name="queryinterface"></a>CComObjectStack::QueryInterface  
 Retourne **E_NOINTERFACE**.  
  
```
HRESULT    QueryInterface(REFIID, void**)
 ;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne **E_NOINTERFACE**.  
  
### <a name="remarks"></a>Remarques  
 En mode débogage, appelle `_ASSERTE`.  
  
##  <a name="a-namereleasea--ccomobjectstackrelease"></a><a name="release"></a>CComObjectStack::Release  
 Retourne zéro.  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne zéro.  
  
### <a name="remarks"></a>Notes  
 En mode débogage, appelle `_ASSERTE`.  
  
## <a name="see-also"></a>Voir aussi  
 [CComAggObject (classe)](../../atl/reference/ccomaggobject-class.md)   
 [Classe de CComObject](../../atl/reference/ccomobject-class.md)   
 [CComObjectGlobal (classe)](../../atl/reference/ccomobjectglobal-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)


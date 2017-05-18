---
title: Classe de CComDynamicUnkArray | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComDynamicUnkArray
- ATLCOM/ATL::CComDynamicUnkArray
- ATLCOM/ATL::CComDynamicUnkArray::CComDynamicUnkArray
- ATLCOM/ATL::CComDynamicUnkArray::Add
- ATLCOM/ATL::CComDynamicUnkArray::begin
- ATLCOM/ATL::CComDynamicUnkArray::clear
- ATLCOM/ATL::CComDynamicUnkArray::end
- ATLCOM/ATL::CComDynamicUnkArray::GetAt
- ATLCOM/ATL::CComDynamicUnkArray::GetCookie
- ATLCOM/ATL::CComDynamicUnkArray::GetSize
- ATLCOM/ATL::CComDynamicUnkArray::GetUnknown
- ATLCOM/ATL::CComDynamicUnkArray::Remove
dev_langs:
- C++
helpviewer_keywords:
- connection points [C++], managing
- CComDynamicUnkArray class
ms.assetid: 202470d7-9a1b-498f-b96d-659d681acd65
caps.latest.revision: 17
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 69fc2c9dbb86f88c85461e765182fd88050521e9
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="ccomdynamicunkarray-class"></a>CComDynamicUnkArray (classe)
Cette classe stocke un tableau de **IUnknown** pointeurs.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class CComDynamicUnkArray
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CComDynamicUnkArray::CComDynamicUnkArray](#ccomdynamicunkarray)|Constructeur. Initialise les valeurs de la collection **NULL** et la taille de la collection à zéro.|  
|[CComDynamicUnkArray :: ~ CComDynamicUnkArray](#dtor)|Destructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CComDynamicUnkArray::Add](#add)|Appelez cette méthode pour ajouter un `IUnknown` pointeur vers le tableau.|  
|[CComDynamicUnkArray::begin](#begin)|Retourne un pointeur vers le premier `IUnknown` pointeur dans la collection.|  
|[CComDynamicUnkArray::clear](#clear)|Vide le tableau.|  
|[CComDynamicUnkArray::end](#end)|Retourne un pointeur vers l’élément suivant le dernier **IUnknown** pointeur dans la collection.|  
|[CComDynamicUnkArray::GetAt](#getat)|Récupère l’élément à l’index spécifié.|  
|[CComDynamicUnkArray::GetCookie](#getcookie)|Appelez cette méthode pour obtenir le cookie associé à une donnée **IUnknown** pointeur.|  
|[CComDynamicUnkArray::GetSize](#getsize)|Retourne la longueur d’un tableau.|  
|[CComDynamicUnkArray::GetUnknown](#getunknown)|Appelez cette méthode pour obtenir le **IUnknown** pointeur associé à un cookie donné.|  
|[CComDynamicUnkArray::Remove](#remove)|Appelez cette méthode pour supprimer un **IUnknown** pointeur à partir du tableau.|  
  
## <a name="remarks"></a>Remarques  
 **CComDynamicUnkArray** contient un tableau alloué dynamiquement de **IUnknown** pointeurs, chacun une interface sur une connexion de point. **CComDynamicUnkArray** peut être utilisé en tant que paramètre à la [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) classe de modèle.  
  
 Le **CComDynamicUnkArray** méthodes [commencer](#begin) et [fin](#end) peut être utilisé pour itérer sur tous les points de connexion (par exemple, lorsqu’un événement est déclenché).  
  
 Consultez la page [Ajout des Points de connexion à un objet](../../atl/adding-connection-points-to-an-object.md) pour plus d’informations sur l’automatisation de la création d’une connexion point proxys.  
  
> [!NOTE]
> **Remarque** la classe **CComDynamicUnkArray** est utilisé par le **ajouter une classe** Assistant lors de la création d’un contrôle qui a des Points de connexion. Si vous souhaitez spécifier manuellement le nombre de Points de connexion, modifiez la référence à partir de **CComDynamicUnkArray** à `CComUnkArray<` *n* `>`, où *n* est le nombre de points de connexion requises.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlcom.h  
  
##  <a name="add"></a>CComDynamicUnkArray::Add  
 Appelez cette méthode pour ajouter un **IUnknown** pointeur vers le tableau.  
  
```
DWORD Add(IUnknown* pUnk);
```  
  
### <a name="parameters"></a>Paramètres  
 *pUnk*  
 Le **IUnknown** pointeur à ajouter au tableau.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le cookie associé le pointeur nouvellement ajouté.  
  
##  <a name="begin"></a>CComDynamicUnkArray::begin  
 Retourne un pointeur vers le début de la collection de **IUnknown** des pointeurs d’interface.  
  
```
IUnknown**
    begin();
```     
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers un **IUnknown** pointeur d’interface.  
  
### <a name="remarks"></a>Notes  
 La collection contient des pointeurs aux interfaces stockées localement en tant que **IUnknown**. Vous effectuez un cast **IUnknown** pour le type d’interface réelle de l’interface, puis appelez par son intermédiaire. Il est inutile d’interroger l’interface tout d’abord.  
  
 Avant d’utiliser la **IUnknown** interface, vous devez vérifier qu’il n’est pas **NULL**.  
  
##  <a name="clear"></a>CComDynamicUnkArray::clear  
 Vide le tableau.  
  
```
void clear();
```  
  
##  <a name="ccomdynamicunkarray"></a>CComDynamicUnkArray::CComDynamicUnkArray  
 Constructeur.  
  
```
CComDynamicUnkArray();
```  
  
### <a name="remarks"></a>Remarques  
 Définit la taille de la collection à zéro et initialise les valeurs à **NULL**. Le destructeur libère de la collection, si nécessaire.  
  
##  <a name="dtor"></a>CComDynamicUnkArray :: ~ CComDynamicUnkArray  
 Destructeur.  
  
```
~CComDynamicUnkArray();
```  
  
### <a name="remarks"></a>Notes  
 Libère les ressources allouées par le constructeur de classe.  
  
##  <a name="end"></a>CComDynamicUnkArray::end  
 Retourne un pointeur vers l’élément suivant le dernier **IUnknown** pointeur dans la collection.  
  
```
IUnknown**
    end();
```     
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers un **IUnknown** pointeur d’interface.  
  
##  <a name="getat"></a>CComDynamicUnkArray::GetAt  
 Récupère l’élément à l’index spécifié.  
  
```
IUnknown* GetAt(int nIndex);
```  
  
### <a name="parameters"></a>Paramètres  
 `nIndex`  
 Index de l'élément à récupérer.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers un [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) interface.  
  
##  <a name="getcookie"></a>CComDynamicUnkArray::GetCookie  
 Appelez cette méthode pour obtenir le cookie associé à une donnée **IUnknown** pointeur.  
  
```
DWORD WINAPI GetCookie(IUnknown** ppFind);
```  
  
### <a name="parameters"></a>Paramètres  
 `ppFind`  
 Le **IUnknown** pointeur pour lequel le cookie associé est nécessaire.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le cookie associé à la **IUnknown** pointeur, ou zéro si aucune correspondance **IUnknown** pointeur est trouvé.  
  
### <a name="remarks"></a>Remarques  
 S’il existe plus d’une instance du même **IUnknown** pointeur, cette fonction renvoie le cookie pour le premier.  
  
##  <a name="getsize"></a>CComDynamicUnkArray::GetSize  
 Retourne la longueur d’un tableau.  
  
```
int GetSize() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Longueur du tableau.  
  
##  <a name="getunknown"></a>CComDynamicUnkArray::GetUnknown  
 Appelez cette méthode pour obtenir le **IUnknown** pointeur associé à un cookie donné.  
  
```
IUnknown* WINAPI GetUnknown(DWORD dwCookie);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwCookie`  
 Le cookie pour lequel associé **IUnknown** pointeur est nécessaire.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le **IUnknown** pointeur, ou NULL si aucun cookie n’est trouvée.  
  
##  <a name="remove"></a>CComDynamicUnkArray::Remove  
 Appelez cette méthode pour supprimer un **IUnknown** pointeur à partir du tableau.  
  
```
BOOL Remove(DWORD dwCookie);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwCookie`  
 Le référencement de cookie le **IUnknown** pointeur à supprimer du tableau.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur TRUE si le pointeur est supprimé ; Sinon, FALSE.  
  
## <a name="see-also"></a>Voir aussi  
 [CComUnkArray (classe)](../../atl/reference/ccomunkarray-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)


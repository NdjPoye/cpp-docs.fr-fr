---
title: Macros de table de service | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: ca02a125-454a-4cf6-aac2-1c5585025ed4
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: eea45a3315237c77eff0231d485111cefb8557cc
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="service-map-macros"></a>Macros de table de service
Ces macros définissent les cartes de services et les entrées.  
  
|||  
|-|-|  
|[BEGIN_SERVICE_MAP](#begin_service_map)|Marque le début d’une table de service ATL.|  
|[END_SERVICE_MAP](#end_service_map)|Marque la fin d’une table de service ATL.|  
|[SERVICE_ENTRY](#service_entry)|Indique que l’objet prend en charge un ID de service spécifique.|  
|[SERVICE_ENTRY_CHAIN](#service_entry_chain)|Fait en sorte que [méthode IServiceProviderImpl::QueryService](#queryservice) à la chaîne de l’objet spécifié.|  

## <a name="requirements"></a>Spécifications  
 **En-tête :** atlcom.h  
   
##  <a name="begin_service_map"></a>BEGIN_SERVICE_MAP  
 Marque le début de la carte de service.  
  
```
BEGIN_SERVICE_MAP(theClass)
```  
  
### <a name="parameters"></a>Paramètres  
 `theClass`  
 [in] Spécifie la classe contenant le mappage de service.  
  
### <a name="remarks"></a>Remarques  
 Pour implémenter des fonctionnalités de fournisseur de service sur votre objet COM, utilisez la carte de service. Tout d’abord, vous devez dériver votre classe de [IServiceProviderImpl](../../atl/reference/iserviceproviderimpl-class.md). Il existe deux types d’entrées :  
  
- [SERVICE_ENTRY](#service_entry) indique la prise en charge pour l’ID (SID) de service spécifié.  
  
- [SERVICE_ENTRY_CHAIN](#service_entry_chain) demande à [méthode IServiceProviderImpl::QueryService](#queryservice) à chaîne à un autre objet spécifié.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_COM&#57;](../../atl/codesnippet/cpp/service-map-macros_1.h)]  
  
##  <a name="end_service_map"></a>END_SERVICE_MAP  
 Marque la fin de la carte de service.  
  
```
END_SERVICE_MAP()
```  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple de [BEGIN_SERVICE_MAP](#begin_service_map).  
  
##  <a name="service_entry"></a>SERVICE_ENTRY  
 Indique que l’objet prend en charge l’id de service spécifié par *SID*.  
  
```
SERVICE_ENTRY( SID )
```  
  
### <a name="parameters"></a>Paramètres  
 *SID*  
 L’ID de service.  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple de [BEGIN_SERVICE_MAP](#begin_service_map).  
  
##  <a name="service_entry_chain"></a>SERVICE_ENTRY_CHAIN  
 Fait en sorte que [méthode IServiceProviderImpl::QueryService](#queryservice) à la chaîne de l’objet spécifié par `punk`.  
  
```
SERVICE_ENTRY_CHAIN( punk )
```  
  
### <a name="parameters"></a>Paramètres  
 `punk`  
 Un pointeur vers le **IUnknown** interface à laquelle à la chaîne.  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple de [BEGIN_SERVICE_MAP](#begin_service_map).  
  
##  <a name="queryservice"></a>Méthode IServiceProviderImpl::QueryService  
 Crée ou accède au service spécifié et retourne un pointeur d’interface pour l’interface spécifiée pour le service.  
  
```
STDMETHOD(QueryService)( 
    REFGUID guidService,
    REFIID riid,
    void** ppvObject);
```  
  
### <a name="parameters"></a>Paramètres  
 [IN]`guidService`  
 Pointeur vers un identificateur de service (SID).  
  
 [IN]`riid`  
 Identificateur de l’interface à laquelle l’appelant doit accéder.  
  
 [OUT]`ppvObj`  
 Pointeur indirect vers l’interface demandée.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourné `HRESULT` valeur est l’une des opérations suivantes :  
  
|Valeur de retour|Signification|  
|------------------|-------------|  
|S_OK|Le service a été correctement créé ou récupéré.|  
|E_INVALIDARG|Un ou plusieurs arguments ne sont pas valides.|  
|E_OUTOFMEMORY|Mémoire insuffisante créer le service.|  
|E_UNEXPECTED|Une erreur inconnue s'est produite.|  
|E_NOINTERFACE|L’interface demandée ne fait pas partie de ce service, ou le service est inconnu.|  
  
### <a name="remarks"></a>Remarques  
 `QueryService`Retourne un pointeur indirect vers l’interface demandée dans le service spécifié. L’appelant est responsable de la libération de ce pointeur lorsqu’il n’est plus nécessaire.  
  
 Lorsque vous appelez `QueryService`, vous passez à la fois un identificateur de service ( `guidService`) et un identificateur d’interface ( `riid`). Le `guidService` Spécifie le service auquel vous souhaitez accéder, et le `riid` identifie une interface qui fait partie du service. En retour, vous recevez un pointeur indirect vers l’interface.  
  
 L’objet qui implémente l’interface peut également implémenter des interfaces qui appartiennent à d’autres services. Considérez ce qui suit :  
  
-   Il se peut que certaines de ces interfaces peuvent être facultatif. Pas toutes les interfaces définies dans la description de service sont nécessairement présents sur toutes les implémentations du service ou sur chaque objet retourné.  
  
-   Contrairement aux appels à `QueryInterface`, en passant un identificateur de service différent ne signifie pas nécessairement qu’un autre objet de modèle COM (Component Object) est retourné.  
  
-   L’objet retourné peut avoir des interfaces supplémentaires qui ne font pas partie de la définition du service.  
  
 Deux services différents, tels que SID_SMyService et SID_SYourService, peuvent tous deux spécifier l’utilisation de la même interface, même si l’implémentation de l’interface n’aient rien en commun entre les deux services. Cela fonctionne, car un appel à `QueryService` (SID_SMyService, IID_IDispatch) peut retourner un objet autre que `QueryService` (SID_SYourService, IID_IDispatch). Identité de l’objet n’est pas supposée lorsque vous spécifiez un identificateur de service différent.  
  
## <a name="see-also"></a>Voir aussi  
 [Macros](../../atl/reference/atl-macros.md)


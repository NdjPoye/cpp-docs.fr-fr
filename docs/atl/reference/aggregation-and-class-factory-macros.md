---
title: "Agrégation et Macros de fabrique de classe | Documents Microsoft"
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
helpviewer_keywords:
- class factories, ATL macros
- aggregation [C++], ATL macros
ms.assetid: d99d379a-0eec-481f-8daa-252dac18f163
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 4509f7be36e45cf96a938e30ec0f82ec0c9836b5
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="aggregation-and-class-factory-macros"></a>Agrégation et Macros de fabrique de classe
Ces macros permettent de contrôler l’agrégation et de déclarer des fabriques de classes.  
  
|||  
|-|-|  
|[DECLARE_AGGREGATABLE](#declare_aggregatable)|Déclare que votre objet peut être agrégée (la valeur par défaut).|  
|[DECLARE_CLASSFACTORY](#declare_classfactory)|Déclare la fabrique de classe [CComClassFactory](../../atl/reference/ccomclassfactory-class.md), la fabrique de classe ATL par défaut.|  
|[DECLARE_CLASSFACTORY_EX](#declare_classfactory_ex)|Déclare votre objet de fabrique de classe à la fabrique de classe.|  
|[MACRO DECLARE_CLASSFACTORY2](#declare_classfactory2)|Déclare [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md) à la fabrique de classe.|  
|[DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread)|Déclare [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) à la fabrique de classe.|  
|[DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton)|Déclare [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md) à la fabrique de classe.|  
|[DECLARE_GET_CONTROLLING_UNKNOWN](#declare_get_controlling_unknown)|Déclare un ordinateur virtuel, `GetControllingUnknown` (fonction).|  
|[DECLARE_NOT_AGGREGATABLE](#declare_not_aggregatable)|Déclare que votre objet ne peut pas être agrégée.|  
|[DECLARE_ONLY_AGGREGATABLE](#declare_only_aggregatable)|Déclare que votre objet doit être agrégée.|  
|[DECLARE_POLY_AGGREGATABLE](#declare_poly_aggregatable)|Vérifie la valeur de l’inconnu extérieur et déclare votre objet peut être agrégé ou non regroupable, le cas échéant.|  
|[MACRO DECLARE_PROTECT_FINAL_CONSTRUCT](#declare_protect_final_construct)|Protège l’objet externe d’une suppression pendant la construction d’un objet interne.|  
|[DECLARE_VIEW_STATUS](#declare_view_status)|Spécifie le **double** indicateurs au conteneur.|  

## <a name="requirements"></a>Spécifications  
 **En-tête :** atlcom.h  
   
##  <a name="declare_aggregatable"></a>DECLARE_AGGREGATABLE  
 Spécifie que l’objet peut être agrégé.  
  
```
DECLARE_AGGREGATABLE( x )
```  
  
### <a name="parameters"></a>Paramètres  
 *x*  
 [in] Le nom de la classe que vous définissez comme agrégées.  
  
### <a name="remarks"></a>Notes  
 [CComCoClass](../../atl/reference/ccomcoclass-class.md) contient cette macro pour spécifier le modèle d’agrégation par défaut. Pour remplacer cette valeur par défaut, spécifiez la [DECLARE_NOT_AGGREGATABLE](#declare_not_aggregatable) ou [DECLARE_ONLY_AGGREGATABLE](#declare_only_aggregatable) macro dans votre définition de classe.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Windowing&#121;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_1.h)]  
  
##  <a name="declare_classfactory"></a>DECLARE_CLASSFACTORY  
 Déclare [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) à la fabrique de classe.  
  
```
DECLARE_CLASSFACTORY()
```  
  
### <a name="remarks"></a>Remarques  
 [CComCoClass](../../atl/reference/ccomcoclass-class.md) utilise cette macro pour déclarer la fabrique de classe par défaut pour votre objet.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_COM&#55;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_2.h)]  
  
##  <a name="ccomclassfactory_class"></a>CComClassFactory (classe)  
 Cette classe implémente le [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364) interface.  
  
```
class CComClassFactory : public IClassFactory,
public CComObjectRootEx<CComGlobalsThreadModel>
```  
  
### <a name="remarks"></a>Notes  
 `CComClassFactory`implémente le [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364) interface qui contient des méthodes pour la création d’un objet d’un CLSID particulier, ainsi que le verrouillage de la fabrique de classe en mémoire pour permettre aux nouveaux objets à créer plus rapidement. **IClassFactory** doit être implémentée pour chaque classe que vous inscrivez dans le Registre système et auquel vous attribuez un CLSID.  
  
 Objets ATL acquièrent normalement une fabrique de classe en dérivant de [CComCoClass](../../atl/reference/ccomcoclass-class.md). Cette classe inclut la macro [DECLARE_CLASSFACTORY](#declare_classfactory), qui déclare `CComClassFactory` en tant que la fabrique de classe par défaut. Pour remplacer cette valeur par défaut, spécifiez l’une de le `DECLARE_CLASSFACTORY` *XXX* macros dans votre définition de classe. Par exemple, le [DECLARE_CLASSFACTORY_EX](#declare_classfactory_ex) macro utilise la classe spécifiée pour la fabrique de classe :  
  
 [!code-cpp[NVC_ATL_COM N °&8;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_3.h)]  
  
 La définition de classe ci-dessus spécifie que **CMyClassFactory** sera utilisé comme fabrique de classe par défaut de l’objet. **CMyClassFactory** doit dériver de `CComClassFactory` et remplacer `CreateInstance`.  
  
 ATL fournit trois autres macros qui déclarent une fabrique de classe :  
  
- [Macro DECLARE_CLASSFACTORY2](#declare_classfactory2) utilise [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md), qui contrôle la création par une licence.  
  
- [DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread) utilise [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md), qui crée des objets dans des compartiments à plusieurs.  
  
- [DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton) utilise [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md), qui construit un seul [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) objet.  
  
##  <a name="declare_classfactory_ex"></a>DECLARE_CLASSFACTORY_EX  
 Déclare `cf` à la fabrique de classe.  
  
```
DECLARE_CLASSFACTORY_EX( cf )
```  
  
### <a name="parameters"></a>Paramètres  
 `cf`  
 [in] Le nom de la classe qui implémente votre objet de fabrique de classe.  
  
### <a name="remarks"></a>Remarques  
 Le `cf` paramètre doit dériver de [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) et remplacer la `CreateInstance` méthode.  
  
 [CComCoClass](../../atl/reference/ccomcoclass-class.md) inclut la [DECLARE_CLASSFACTORY](#declare_classfactory) (macro), qui spécifie `CComClassFactory` comme la fabrique de classe par défaut. Toutefois, en incluant le `DECLARE_CLASSFACTORY_EX` macro dans la définition de classe de votre objet, vous remplacez cette valeur par défaut.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_COM N °&8;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_3.h)]  
  
##  <a name="declare_classfactory2"></a>MACRO DECLARE_CLASSFACTORY2  
 Déclare [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md) à la fabrique de classe.  
  
```
DECLARE_CLASSFACTORY2( lic )
```  
  
### <a name="parameters"></a>Paramètres  
 *contrat de licence d'*  
 [in] Une classe qui implémente `VerifyLicenseKey`, `GetLicenseKey`, et `IsLicenseValid`.  
  
### <a name="remarks"></a>Remarques  
 [CComCoClass](../../atl/reference/ccomcoclass-class.md) inclut la [DECLARE_CLASSFACTORY](#declare_classfactory) (macro), laquelle spécifie [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) en tant que la fabrique de classe par défaut. Toutefois, en incluant le `DECLARE_CLASSFACTORY2` macro dans la définition de classe de votre objet, vous remplacez cette valeur par défaut.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_COM N °&2;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_4.h)]  
  
##  <a name="ccomclassfactory2_class"></a>CComClassFactory2 (classe)  
 Cette classe implémente le [IClassFactory2](http://msdn.microsoft.com/library/windows/desktop/ms692720) interface.  
  
```
template <class license>
class  CComClassFactory2 : public IClassFactory2,
    public CComObjectRootEx<CComGlobalsThreadModel>,
    public license
```    
  
### <a name="parameters"></a>Paramètres  
 *licence*  
 Une classe qui implémente les fonctions statiques suivantes :  
  
- **static BOOL VerifyLicenseKey (BSTR** `bstr` **) ;**  
  
- **static BOOL GetLicenseKey (DWORD** `dwReserved` **, BSTR\* ** `pBstr` **) ;**  
  
- **statique (de) BOOL IsLicenseValid ;**  
  
### <a name="remarks"></a>Remarques  
 `CComClassFactory2`implémente le [IClassFactory2](http://msdn.microsoft.com/library/windows/desktop/ms692720) interface, qui est une extension de [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364). **IClassFactory2** contrôles création une licence par le biais d’un objet. Une fabrique de classe s’exécutant sur un ordinateur sous licence peut fournir une clé de licence d’exécution. Cette clé de licence permet à une application instancier des objets lorsqu’une licence complète ordinateur n’existe pas.  
  
 Objets ATL acquièrent normalement une fabrique de classe en dérivant de [CComCoClass](../../atl/reference/ccomcoclass-class.md). Cette classe inclut la macro [DECLARE_CLASSFACTORY](#declare_classfactory), qui déclare [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) en tant que la fabrique de classe par défaut. Pour utiliser `CComClassFactory2`, spécifiez la [macro DECLARE_CLASSFACTORY2](#declare_classfactory2) macro dans la définition de classe de votre objet. Exemple :  
  
 [!code-cpp[NVC_ATL_COM N °&2;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_4.h)]  
  
 **CMyLicense**, le paramètre de modèle `CComClassFactory2`, doivent implémenter les fonctions statiques `VerifyLicenseKey`, `GetLicenseKey`, et `IsLicenseValid`. Voici un exemple d’une classe simple de licence :  
  
 [!code-cpp[NVC_ATL_COM N °&3;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_5.h)]  
  
 `CComClassFactory2`dérive les deux **CComClassFactory2Base** et *licence*. **CComClassFactory2Base**, à son tour, dérive de **IClassFactory2** et **CComObjectRootEx\< CComGlobalsThreadModel >**.  
  
##  <a name="declare_classfactory_auto_thread"></a>DECLARE_CLASSFACTORY_AUTO_THREAD  
 Déclare [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) à la fabrique de classe.  
  
```
DECLARE_CLASSFACTORY_AUTO_THREAD()
```  
  
### <a name="remarks"></a>Remarques  
 [CComCoClass](../../atl/reference/ccomcoclass-class.md) inclut la [DECLARE_CLASSFACTORY](#declare_classfactory) (macro), laquelle spécifie [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) en tant que la fabrique de classe par défaut. Toutefois, en incluant le `DECLARE_CLASSFACTORY_AUTO_THREAD` macro dans la définition de classe de votre objet, vous remplacez cette valeur par défaut.  
  
 Lorsque vous créez des objets dans des compartiments multiples (dans un serveur out-of-process), ajoutez `DECLARE_CLASSFACTORY_AUTO_THREAD` à votre classe.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_COM&#9;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_6.h)]  
  
##  <a name="ccomclassfactoryautothread_class"></a>CComClassFactoryAutoThread (classe)  
 Cette classe implémente le [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364) de l’interface et permet aux objets d’être créés dans des compartiments à plusieurs.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peut pas être utilisées dans les applications qui s’exécutent dans le Windows Runtime.  
  
```
class CComClassFactoryAutoThread : public IClassFactory,
public CComObjectRootEx<CComGlobalsThreadModel>
```  
  
### <a name="remarks"></a>Remarques  
 `CComClassFactoryAutoThread`est semblable à [CComClassFactory](../../atl/reference/ccomclassfactory-class.md), mais permet aux objets d’être créés dans des compartiments à plusieurs. Pour tirer parti de cette prise en charge, dérivez votre module EXE à partir de [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md).  
  
 Objets ATL acquièrent normalement une fabrique de classe en dérivant de [CComCoClass](../../atl/reference/ccomcoclass-class.md). Cette classe inclut la macro [DECLARE_CLASSFACTORY](#declare_classfactory), qui déclare [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) en tant que la fabrique de classe par défaut. Pour utiliser `CComClassFactoryAutoThread`, spécifiez la [DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread) macro dans la définition de classe de votre objet. Exemple :  
  
 [!code-cpp[NVC_ATL_COM&#9;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_6.h)]  
  
##  <a name="declare_classfactory_singleton"></a>DECLARE_CLASSFACTORY_SINGLETON  
 Déclare [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md) à la fabrique de classe.  
  
```
DECLARE_CLASSFACTORY_SINGLETON( obj )
```  
  
### <a name="parameters"></a>Paramètres  
 `obj`  
 [in] Le nom de votre objet de classe.  
  
### <a name="remarks"></a>Notes  
 [CComCoClass](../../atl/reference/ccomcoclass-class.md) inclut la [DECLARE_CLASSFACTORY](#declare_classfactory) (macro), laquelle spécifie [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) en tant que la fabrique de classe par défaut. Toutefois, en incluant le `DECLARE_CLASSFACTORY_SINGLETON` macro dans la définition de classe de votre objet, vous remplacez cette valeur par défaut.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_COM&#10;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_7.h)]  
  
##  <a name="ccomclassfactorysingleton_class"></a>CComClassFactorySingleton (classe)  
 Cette classe dérive de [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) et utilise [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) pour construire un objet unique.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peut pas être utilisées dans les applications qui s’exécutent dans le Windows Runtime.  
  
```
template<class T>
class CComClassFactorySingleton : public CComClassFactory
```  
  
### <a name="parameters"></a>Paramètres  
 `T`  
 Votre classe.  
  
 `CComClassFactorySingleton`dérive de [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) et utilise [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) pour construire un objet unique. Chaque appel à la `CreateInstance` méthode interroge simplement un pointeur d’interface de cet objet.  
  
### <a name="remarks"></a>Remarques  
 Objets ATL acquièrent normalement une fabrique de classe en dérivant de [CComCoClass](../../atl/reference/ccomcoclass-class.md). Cette classe inclut la macro [DECLARE_CLASSFACTORY](#declare_classfactory), qui déclare `CComClassFactory` en tant que la fabrique de classe par défaut. Pour utiliser `CComClassFactorySingleton`, spécifiez la [DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton) macro dans la définition de classe de votre objet. Exemple :  
  
 [!code-cpp[NVC_ATL_COM&#10;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_7.h)]  
  
##  <a name="declare_get_controlling_unknown"></a>DECLARE_GET_CONTROLLING_UNKNOWN  
 Déclare une fonction virtuelle `GetControllingUnknown`.  
  
```
DECLARE_GET_CONTROLLING_UNKNOWN()
```  
  
### <a name="remarks"></a>Notes  
 Ajouter cette macro à votre objet, si vous obtenez le message d’erreur du compilateur `GetControllingUnknown` n’est pas défini (par exemple, dans **CComAggregateCreator**).  
  
##  <a name="declare_not_aggregatable"></a>DECLARE_NOT_AGGREGATABLE  
 Spécifie que l’objet ne peut pas être agrégée.  
  
```
DECLARE_NOT_AGGREGATABLE( x )
```  
  
### <a name="parameters"></a>Paramètres  
 *x*  
 [in] Le nom de l’objet que vous définissez en tant que ne peut pas être agrégé.  
  
### <a name="remarks"></a>Remarques  
 `DECLARE_NOT_AGGREGATABLE`entraîne `CreateInstance` pour retourner une erreur ( **CLASS_E_NOAGGREGATION**) si une tentative est faite à agréger sur votre objet.  
  
 Par défaut, [CComCoClass](../../atl/reference/ccomcoclass-class.md) contient le [DECLARE_AGGREGATABLE](#declare_aggregatable) (macro), ce qui indique que votre objet peut être agrégée. Pour remplacer ce comportement par défaut, incluez `DECLARE_NOT_AGGREGATABLE` dans votre définition de classe.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Windowing&#121;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_1.h)]  
  
##  <a name="declare_only_aggregatable"></a>DECLARE_ONLY_AGGREGATABLE  
 Spécifie que l’objet doit être agrégée.  
  
```
DECLARE_ONLY_AGGREGATABLE( x )
```  
  
### <a name="parameters"></a>Paramètres  
 *x*  
 [in] Le nom de l’objet que vous définissez comme uniquement peut être agrégé.  
  
### <a name="remarks"></a>Remarques  
 `DECLARE_ONLY_AGGREGATABLE`provoque une erreur ( **E_FAIL**) si une tentative est faite pour **CoCreate** votre objet comme objet non regroupées en agrégats.  
  
 Par défaut, [CComCoClass](../../atl/reference/ccomcoclass-class.md) contient le [DECLARE_AGGREGATABLE](#declare_aggregatable) (macro), ce qui indique que votre objet peut être agrégée. Pour remplacer ce comportement par défaut, incluez `DECLARE_ONLY_AGGREGATABLE` dans votre définition de classe.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Windowing&#125;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_8.h)]  
  
##  <a name="declare_poly_aggregatable"></a>DECLARE_POLY_AGGREGATABLE  
 Spécifie qu’une instance de **CComPolyObject \< ** *x* ** > ** créée lors de la création de votre objet.  
  
```
DECLARE_POLY_AGGREGATABLE( x )
```  
  
### <a name="parameters"></a>Paramètres  
 *x*  
 [in] Le nom de l’objet que vous définissez comme agrégées ou ne peut pas être agrégé.  
  
### <a name="remarks"></a>Remarques  
 Lors de la création, la valeur de l’inconnu extérieur est vérifiée. S’il s’agit **NULL**, **IUnknown** est implémenté pour un objet non regroupées en agrégats. Si l’inconnu extérieur n’est pas **NULL**, **IUnknown** est implémenté pour un objet.  
  
 L’avantage de l’utilisation de `DECLARE_POLY_AGGREGATABLE` est que vous n’avez pas à la fois `CComAggObject` et `CComObject` dans votre module pour gérer les cas regroupés et. Un seul `CComPolyObject` objet gère les deux cas. Cela ne signifie qu’une seule copie de vtable et une seule copie des fonctions existent dans votre module. Si votre vtable est importante, cela peut réduire considérablement la taille de votre module. Toutefois, si votre vtable est petite, à l’aide de `CComPolyObject` peut entraîner une taille légèrement supérieure du module car il n’est pas optimisé pour un objet regroupé ou, comme `CComAggObject` et `CComObject`.  
  
 Le `DECLARE_POLY_AGGREGATABLE` macro est automatiquement déclaré dans votre objet si vous utilisez l’Assistant contrôle ATL pour créer un contrôle total.  
  
##  <a name="declare_protect_final_construct"></a>MACRO DECLARE_PROTECT_FINAL_CONSTRUCT  

 Protège votre objet d’être supprimé si (pendant [FinalConstruct](ccomobjectrootex-class.md#finalconstruct)) l’objet interne agrégée incrémente le décompte de références puis décrémente le nombre de 0.  
  
```
DECLARE_PROTECT_FINAL_CONSTRUCT()
```  
  
##  <a name="declare_view_status"></a>DECLARE_VIEW_STATUS  
 Placez cette macro dans la classe de contrôle d’un contrôle ActiveX ATL pour spécifier le **double** indicateurs au conteneur.  
  
```
DECLARE_VIEW_STATUS( statusFlags )
```  
  
### <a name="parameters"></a>Paramètres  
 `statusFlags`  
 [in] Le **double** indicateurs. Consultez la page [double](http://msdn.microsoft.com/library/windows/desktop/ms687201) pour obtenir la liste d’indicateurs.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Windowing&#126;](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_9.h)]  
  
## <a name="see-also"></a>Voir aussi  
 [Macros](../../atl/reference/atl-macros.md)


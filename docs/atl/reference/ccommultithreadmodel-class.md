---
title: Classe de CComMultiThreadModel | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComMultiThreadModel
- ATL.CComMultiThreadModel
- ATL::CComMultiThreadModel
dev_langs:
- C++
helpviewer_keywords:
- ATL, multithreading
- CComMultiThreadModel class
- threading [ATL]
ms.assetid: db8f1662-2f7a-44b3-b341-ffbfb6e422a3
caps.latest.revision: 21
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
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 6dbfb33a717b23e8252c9bcb2fc11b4a6e420280
ms.lasthandoff: 02/24/2017

---
# <a name="ccommultithreadmodel-class"></a>CComMultiThreadModel (classe)
`CComMultiThreadModel`Fournit des méthodes thread-safe pour incrémenter et décrémenter la valeur d’une variable.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class CComMultiThreadModel
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-typedefs"></a>Typedefs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CComMultiThreadModel::AutoCriticalSection](#autocriticalsection)|Fait référence à la classe [CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md).|  
|[CComMultiThreadModel::CriticalSection](#criticalsection)|Fait référence à la classe [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md).|  
|[CComMultiThreadModel::ThreadModelNoCS](#threadmodelnocs)|Fait référence à la classe [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md).|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CComMultiThreadModel::Decrement](#decrement)|(Statique) Décrémente la valeur de la variable spécifiée de manière thread-safe.|  
|[CComMultiThreadModel::Increment](#increment)|(Statique) Incrémente la valeur de la variable spécifiée de manière thread-safe.|  
  
## <a name="remarks"></a>Notes  
 En général, vous utilisez `CComMultiThreadModel` via un des deux `typedef` noms, soit [CComObjectThreadModel] (atl-typedefs.md #ccomobjectthreadmodel ou [CComGlobalsThreadModel] (atl-typedefs.md #ccomglobalsthreadmodel. La classe référencée par chaque `typedef` varie selon le modèle de thread utilisé, comme indiqué dans le tableau suivant :  
  
|typedef|Thread unique|Modèle de thread cloisonné|Modèle de thread libre|  
|-------------|----------------------|-------------------------|--------------------|  
|`CComObjectThreadModel`|S|S|M|  
|`CComGlobalsThreadModel`|S|M|M|  
  
 S= `CComSingleThreadModel`; M =`CComMultiThreadModel`  
  
 `CComMultiThreadModel`lui-même définit trois `typedef` noms. `AutoCriticalSection`et `CriticalSection` référencer des classes qui fournissent des méthodes permettant d’obtenir et de libérer la possession d’une section critique. `ThreadModelNoCS`références de classe [CComMultiThreadModelNoCS(ccommultithreadmodelnocs-class.md).  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlbase.h  
  
##  <a name="a-nameautocriticalsectiona--ccommultithreadmodelautocriticalsection"></a><a name="autocriticalsection"></a>CComMultiThreadModel::AutoCriticalSection  
 Lorsque vous utilisez `CComMultiThreadModel`, le `typedef` nom `AutoCriticalSection` fait référence à la classe [CComAutoCriticalSection](ccomautocriticalsection-class.md), qui fournit des méthodes pour obtenir et de libérer la possession d’un objet de section critique.  
  
```
typedef CComAutoCriticalSection AutoCriticalSection;
```  
  
### <a name="remarks"></a>Notes  
 [CComSingleThreadModel](ccomsinglethreadmodel-class.md) et [CComMultiThreadModelNoCS](ccommultithreadmodelnocs-class.md) contiennent également des définitions pour `AutoCriticalSection`. Le tableau suivant montre la relation entre la classe de modèle de thread et la classe de section critique référencée par `AutoCriticalSection`:  
  
|Classe définie dans|Classe référencée|  
|----------------------|----------------------|  
|`CComMultiThreadModel`|`CComCriticalSection`|  
|`CComSingleThreadModel`|`CComFakeCriticalSection`|  
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|  
  
 En plus de `AutoCriticalSection`, vous pouvez utiliser la `typedef` nom [CriticalSection](#criticalsection). Vous ne devez pas spécifier `AutoCriticalSection` dans des objets globaux ou des membres de classe statique si vous souhaitez supprimer le code de démarrage CRT.  
  
### <a name="example"></a>Exemple  
 Le code suivant est modélisé d’après [CComObjectRootEx](ccomobjectrootex-class.md)et illustre `AutoCriticalSection` utilisé dans un environnement de thread.  
  

```cpp  
template<class ThreadModel>
class CMyAutoCritClass
{
public:
   typedef ThreadModel _ThreadModel;
   typedef typename _ThreadModel::AutoCriticalSection _CritSec;

   CMyAutoCritClass() : m_dwRef(0) {}

   ULONG InternalAddRef()
   {
      return _ThreadModel::Increment(&m_dwRef);
   }
   ULONG InternalRelease()
   {
      return _ThreadModel::Decrement(&m_dwRef);   
   }
   void Lock() { m_critsec.Lock( ); }
   void Unlock() { m_critsec.Unlock(); }

private:
   _CritSec m_critsec;
   LONG m_dwRef;
```  
  
 Les tableaux suivants indiquent les résultats de la `InternalAddRef` et `Lock` méthodes, selon le **ThreadModel** paramètre de modèle et le modèle de thread utilisé par l’application :  
  
### <a name="threadmodel--ccomobjectthreadmodel"></a>ThreadModel = CComObjectThreadModel  
  
|Méthode|Unique ou modèle de thread cloisonné|Modèle de thread libre|  
|------------|-----------------------------------|--------------------|  
|`InternalAddRef`|L’incrément n’est pas thread-safe.|L’incrément est thread-safe.|  
|`Lock`|N’a aucun effet ; Il n’existe aucune section critique à verrouiller.|La section critique est verrouillée.|  
  
### <a name="threadmodel--ccomobjectthreadmodelthreadmodelnocs"></a>ThreadModel = CComObjectThreadModel::ThreadModelNoCS  
  
|Méthode|Unique ou modèle de thread cloisonné|Modèle de thread libre|  
|------------|-----------------------------------|--------------------|  
|`InternalAddRef`|L’incrément n’est pas thread-safe.|L’incrément est thread-safe.|  
|`Lock`|N’a aucun effet ; Il n’existe aucune section critique à verrouiller.|N’a aucun effet ; Il n’existe aucune section critique à verrouiller.|  
  
##  <a name="a-namecriticalsectiona--ccommultithreadmodelcriticalsection"></a><a name="criticalsection"></a>CComMultiThreadModel::CriticalSection  
 Lorsque vous utilisez `CComMultiThreadModel`, le `typedef` nom `CriticalSection` fait référence à la classe [CComCriticalSection](ccomcriticalsection-class.md), qui fournit des méthodes pour obtenir et de libérer la possession d’un objet de section critique.  
  
```
typedef CComCriticalSection CriticalSection;
```  
  
### <a name="remarks"></a>Remarques  
 [CComSingleThreadModel](ccomsinglethreadmodel-class.md) et [CComMultiThreadModelNoCS](ccommultithreadmodelnocs-class.md) contiennent également des définitions pour `CriticalSection`. Le tableau suivant montre la relation entre la classe de modèle de thread et la classe de section critique référencée par `CriticalSection`:  
  
|Classe définie dans|Classe référencée|  
|----------------------|----------------------|  
|`CComMultiThreadModel`|`CComCriticalSection`|  
|`CComSingleThreadModel`|`CComFakeCriticalSection`|  
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|  
  
 En plus de `CriticalSection`, vous pouvez utiliser la `typedef` nom [AutoCriticalSection](#autocriticalsection). Vous ne devez pas spécifier `AutoCriticalSection` dans des objets globaux ou des membres de classe statique si vous souhaitez supprimer le code de démarrage CRT.  
  
### <a name="example"></a>Exemple  
 Consultez la page [CComMultiThreadModel::AutoCriticalSection](#autocriticalsection).  
  
##  <a name="a-namedecrementa--ccommultithreadmodeldecrement"></a><a name="decrement"></a>CComMultiThreadModel::Decrement  
 Cette fonction statique appelle la fonction Win32 [InterlockedDecrement](http://msdn.microsoft.com/library/windows/desktop/ms683580), qui décrémente la valeur de la variable vers laquelle pointe `p`.  
  
```
static ULONG WINAPI Decrement(LPLONG p) throw ();
```  
  
### <a name="parameters"></a>Paramètres  
 `p`  
 [in] Pointeur vers la variable à décrémenter.  
  
### <a name="return-value"></a>Valeur de retour  
 Si le résultat de la décrémentation est 0, puis `Decrement` retourne 0. Si le résultat de la décrémentation est différente de zéro, la valeur de retour est également différente de zéro, mais ne peut-être pas égaler le résultat de la décrémentation.  
  
### <a name="remarks"></a>Remarques  
 **InterlockedDecrement** empêche que plusieurs threads simultanément à l’aide de cette variable.  
  
##  <a name="a-nameincrementa--ccommultithreadmodelincrement"></a><a name="increment"></a>CComMultiThreadModel::Increment  
 Cette fonction statique appelle la fonction Win32 [InterlockedIncrement](http://msdn.microsoft.com/library/windows/desktop/ms683614), qui incrémente la valeur de la variable vers laquelle pointée `p`.  
  
```
static ULONG WINAPI Increment(LPLONG p) throw ();
```  
  
### <a name="parameters"></a>Paramètres  
 `p`  
 [in] Pointeur vers la variable à incrémenter.  
  
### <a name="return-value"></a>Valeur de retour  
 Si le résultat de l’incrément est 0, puis **incrément** retourne 0. Si le résultat de l’incrément est différente de zéro, la valeur de retour est également différente de zéro, mais le résultat de l’incrément ne peut pas égaler.  
  
### <a name="remarks"></a>Notes  
 **InterlockedIncrement** empêche que plusieurs threads simultanément à l’aide de cette variable.  
  
##  <a name="a-namethreadmodelnocsa--ccommultithreadmodelthreadmodelnocs"></a><a name="threadmodelnocs"></a>CComMultiThreadModel::ThreadModelNoCS  
 Lorsque vous utilisez `CComMultiThreadModel`, le `typedef` nom `ThreadModelNoCS` fait référence à la classe [CComMultiThreadModelNoCS](ccommultithreadmodelnocs-class.md).  
  
```
typedef CComMultiThreadModelNoCS ThreadModelNoCS;
```  
  
### <a name="remarks"></a>Remarques  
 `CComMultiThreadModelNoCS`Fournit des méthodes thread-safe pour incrémenter et décrémenter une variable ; Toutefois, il ne fournit pas une section critique.  
  
 [CComSingleThreadModel](ccomsinglethreadmodel-class.md) et `CComMultiThreadModelNoCS` contiennent également des définitions pour `ThreadModelNoCS`. Le tableau suivant montre la relation entre la classe de modèle de thread et la classe référencée par `ThreadModelNoCS`:  
  
|Classe définie dans|Classe référencée|  
|----------------------|----------------------|  
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|  
|`CComSingleThreadModel`|`CComSingleThreadModel`|  
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|  
  
### <a name="example"></a>Exemple  
 Consultez la page [CComMultiThreadModel::AutoCriticalSection](#autocriticalsection).  
  
## <a name="see-also"></a>Voir aussi  
 [CComSingleThreadModel (classe)](ccomsinglethreadmodel-class.md)   
 [CComAutoCriticalSection (classe)](ccomautocriticalsection-class.md)   
 [CComCriticalSection (classe)](ccomcriticalsection-class.md)   
 [Vue d’ensemble de la classe](../atl-class-overview.md)


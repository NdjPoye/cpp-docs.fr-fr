---
title: 'Classe Platform::Collections :: vectorview | Documents Microsoft'
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::VectorView::VectorView
- COLLECTION/Platform::Collections::VectorView::First
- COLLECTION/Platform::Collections::VectorView::GetAt
- COLLECTION/Platform::Collections::VectorView::GetMany
- COLLECTION/Platform::Collections::VectorView::IndexOf
- COLLECTION/Platform::Collections::VectorView::Size
dev_langs:
- C++
helpviewer_keywords:
- VectorView Class
ms.assetid: 05cd461d-dce7-49d3-b0e7-2e5c78ed8192
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 937342c340b085f2e2bdeef8ed7df21dae826152
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="platformcollectionsvectorview-class"></a>Platform::Collections::VectorView, classe
Représente une vue en lecture seule d'une collection d'objets séquentielle qui peut être accessible individuellement par index. Le type de chaque objet de la collection est défini par le paramètre de modèle.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <typename T, typename E>  
   ref class VectorView sealed;  
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Type des éléments contenus dans l'objet `VectorView` .  
  
 `E`  
 Spécifie un prédicat binaire pour tester l'égalité des valeurs de type `T`. La valeur par défaut est `std::equal_to<T>`.  
  
### <a name="remarks"></a>Notes  
 Le `VectorView` la classe implémente le [Windows::Foundation::Collections::IVectorView\<T >](http://go.microsoft.com/fwlink/p/?LinkId=262411) interface et la prise en charge des itérateurs Standard Template Library.  
  
### <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[VectorView::VectorView](#ctor)|Initialise une nouvelle instance de la classe VectorView.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[VectorView::First](#first)|Retourne un itérateur qui spécifie le premier élément du VectorView.|  
|[VectorView::GetAt](#getat)|Récupère l'élément du VectorView actuel qui est indiqué par l'index spécifié.|  
|[VectorView::GetMany](#getmany)|Récupère une séquence d'éléments du VectorView actif en commençant à l'index spécifié.|  
|[VectorView::IndexOf](#indexof)|Recherche l'élément spécifié dans l'objet VectorView actuel, et s'il existe, retourne l'index de l'élément.|  
|[VectorView::Size](#size)|Retourne le nombre d'éléments dans l'objet VectorView actuel.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 `VectorView`  
  
### <a name="requirements"></a>Spécifications  
 **En-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  

## <a name="first"></a>  VectorView::First (méthode)
Retourne un itérateur qui spécifie le premier élément du VectorView.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
  
virtual Windows::Foundation::Collections::IIterator<T>^   
   First();  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Itérateur qui spécifie le premier élément de l'objet VectorView.  
  
### <a name="remarks"></a>Notes  
 Un moyen pratique de contenir l’itérateur retourné par First() est d’assigner la valeur de retournée à une variable déclarée avec le **automatique** mot clé de déduction de type. Par exemple, `auto x = myVectorView->First();`.  
  


## <a name="getat"></a>  VectorView::GetAt (méthode)
Récupère l'élément du VectorView actuel qui est indiqué par l'index spécifié.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
  
T GetAt(  
   UInt32 index  
);  
```  
  
### <a name="parameters"></a>Paramètres  
 `index`  
 Entier non signé de base zéro qui spécifie un élément particulier dans l’objet VectorView.  
  
### <a name="return-value"></a>Valeur de retour  
 Élément spécifié par le paramètre `index`. Le type d’élément spécifié par le paramètre de modèle VectorView *T*.  
  


## <a name="getmany"></a>  VectorView::GetMany (méthode)
Récupère une séquence d'éléments du VectorView actif en commençant à l'index spécifié.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
  
virtual unsigned int GetMany(  
   unsigned int startIndex,   
   ::Platform::WriteOnlyArray<T>^ dest  
);  
```  
  
### <a name="parameters"></a>Paramètres  
 `startIndex`  
 L'index de base zéro du début des éléments à récupérer.  
  
 `dest`  
 Lorsque cette opération est terminée, un tableau d’éléments qui commencent à l’élément spécifié par `startIndex` et se terminent au dernier élément du vectorview.  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre d'éléments à récupérer.  
  


## <a name="indexof"></a>  VectorView::IndexOf (méthode)
Recherche l'élément spécifié dans l'objet VectorView actuel, et s'il existe, retourne l'index de l'élément.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
  
virtual bool IndexOf(  
   T value,  
   unsigned int* index  
);  
```  
  
### <a name="parameters"></a>Paramètres  
 `value`  
 Élément à rechercher.  
  
 `index`  
 Index de base zéro de l'élément si le paramètre `value` est détecté ; sinon, 0.  
  
 Le paramètre `index` est égal à 0 si l'élément est le premier élément du VectorView ou que l'élément est introuvable. Si la valeur de retour est `true`, l'élément est trouvé et représente le premier élément ; sinon, l'élément est introuvable.  
  
### <a name="return-value"></a>Valeur de retour  
 `true` si l'élément spécifié est trouvé ; sinon, `false`.  
  


## <a name="size"></a>  Vectorview::Size, méthode
Retourne le nombre d'éléments dans l'objet VectorView actuel.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
  
virtual property unsigned int Size;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Nombre d’éléments dans le VectorView actuel.  
  


## <a name="ctor"></a>  VectorView::VectorView (constructeur)
Initialise une nouvelle instance de la classe VectorView.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
VectorView();  
explicit VectorView(  
   UInt32 size  
);  
VectorView(  
   UInt32 size,  
   T value  
);  
explicit VectorView(  
   const ::std::vector<T>& v  
);  
explicit VectorView(  
   ::std::vector<T>&& v  
);  
VectorView(  
   const T * ptr,  
   UInt32 size  
);  
  
template <  
   size_t N  
>  
explicit VectorView(  
   const T (&arr)[N]  
);  
  
template <  
   size_t N  
>  
explicit VectorView(  
   const ::std::array<T,  
   N>& a  
);  
  
explicit VectorView(  
   const ::Platform::Array<T>^ arr  
);  
  
template <  
   typename InIt  
>  
VectorView(  
   InItfirst,  
   InItlast  
);  
  
VectorView(  
   std::initializer_list<T> il  
);  
```  
  
### <a name="parameters"></a>Paramètres  
 `InIt`  
 Type d’une collection d’objets utilisée pour initialiser le VectorView actif.  
  
 il  
 A [std::initializer_list](../standard-library/initializer-list-class.md) dont les éléments seront utilisés pour initialiser le VectorView.  
  
 `N`  
 Nombre d’éléments d’une collection d’objets utilisée pour initialiser le VectorView actif.  
  
 `size`  
 Nombre d'éléments du VectorView.  
  
 `value`  
 Valeur utilisée pour initialiser chaque élément du VectorView actif.  
  
 `v`  
 Un [Lvalues et Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md) à un [std::vector](../standard-library/vector-class.md) qui est utilisé pour initialiser le VectorView actif.  
  
 `ptr`  
 Pointeur vers un `std::vector` utilisé pour initialiser le VectorView actif.  
  
 `arr`  
 A [Platform::Array](../cppcx/platform-array-class.md) objet qui est utilisé pour initialiser le VectorView actif.  
  
 `a`  
 A [std::array](../standard-library/array-class-stl.md) objet qui est utilisé pour initialiser le VectorView actif.  
  
 `first`  
 Premier élément d'une séquence d'objets utilisée pour initialiser le VectorView actif. Le type de `first` est passé à l’aide de *un transfert parfait*. Pour plus d'informations, consultez [Déclarateur de référence rvalue : &&](../cpp/rvalue-reference-declarator-amp-amp.md).  
  
 `last`  
 Dernier élément d'une séquence d'objets utilisée pour initialiser le VectorView actif. Le type de `last` est passé à l’aide de *un transfert parfait*. Pour plus d'informations, consultez [Déclarateur de référence rvalue : &&](../cpp/rvalue-reference-declarator-amp-amp.md).  
  


  
## <a name="see-also"></a>Voir aussi  
 [Plateforme Namespace](platform-namespace-c-cx.md)   
 [Création de composants Windows Runtime en C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)
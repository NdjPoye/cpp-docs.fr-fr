---
title: "Classe Platform::Collections :: Vector | Documents Microsoft"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- COLLECTION/Platform::Collections::Vector::Vector
- COLLECTION/Platform::Collections::Vector::Append
- COLLECTION/Platform::Collections::Vector::Clear
- COLLECTION/Platform::Collections::Vector::First
- COLLECTION/Platform::Collections::Vector::GetAt
- COLLECTION/Platform::Collections::Vector::GetMany
- COLLECTION/Platform::Collections::Vector::GetView
- COLLECTION/Platform::Collections::Vector::IndexOf
- COLLECTION/Platform::Collections::Vector::InsertAt
- COLLECTION/Platform::Collections::Vector::ReplaceAll
- COLLECTION/Platform::Collections::Vector::RemoveAt
- COLLECTION/Platform::Collections::Vector::RemoveAtEnd
- COLLECTION/Platform::Collections::Vector::SetAt
- COLLECTION/Platform::Collections::Vector::Size
- COLLECTION/Platform::Collections::Vector::VectorChanged
dev_langs: C++
helpviewer_keywords: Vector Class (C++/Cx)
ms.assetid: aee8c076-9700-47c3-99b6-799fd3edb0ca
caps.latest.revision: "17"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8c371b6805616ff0b114be24bb291469eae2dd26
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="platformcollectionsvector-class"></a>Platform::Collections::Vector, classe
Représente une collection séquentielle d'objets accessibles séparément par index.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <typename T, typename E>  
   ref class Vector sealed;  
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Type des éléments contenus dans l'objet Vector.  
  
 `E`  
 Spécifie un prédicat binaire pour tester l'égalité des valeurs de type `T`. La valeur par défaut est `std::equal_to<T>`.  
  
### <a name="remarks"></a>Notes  
 Les types autorisés sont les suivants :  
  
1.  Entiers  
  
2.  Classe interface ^  
  
3.  Classe ref publique ^  
  
4.  value struct  
  
5.  classe d'énumération publique  
  
 La classe Vector est l'implémentation concrète C++ de l'interface [Windows::Foundation::Collections::IVector](http://go.microsoft.com/fwlink/p/?LinkId=262410) .  
  
 Si vous tentez d'utiliser un type Vector dans une valeur ou un paramètre de retour public, l'erreur de compilateur C3986 est générée. Vous pouvez corriger l'erreur en modifiant le type du paramètre ou le type de la valeur de retour par [Windows::Foundation::Collections::IVector](http://go.microsoft.com/fwlink/p/?LinkId=262410). Pour plus d'informations, consultez [Collections (C++/CX)](../cppcx/collections-c-cx.md).  
  
### <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[Vector::Vector](#ctor)|Initialise une nouvelle instance de la classe Vector.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[Vector::Append](#append)|Insère l'élément spécifié après le dernier élément du Vector actif.|  
|[Vector::Clear](#clear)|Supprime tous les éléments du vecteur actuel.|  
|[Vector::First](#first)|Retourne un itérateur qui spécifie le premier élément du Vector.|  
|[Vector::GetAt](#getat)|Récupère l'élément de l'objet Vector actuel qui est identifié par l'index spécifié.|  
|[Vector::GetMany](#getmany)|Récupère une séquence d'éléments du Vector actif en commençant à l'index spécifié.|  
|[Vector::GetView](#getview)|Retourne une vue en lecture seule d'un vecteur ; autrement dit, une [Platform::Collections::VectorView](../cppcx/platform-collections-vectorview-class.md).|  
|[Vector::IndexOf](#indexof)|Recherche l'élément spécifié dans l'objet Vector actuel, et s'il existe, retourne l'index de l'élément.|  
|[Vector::InsertAt](#insertat)|Insère l'élément spécifié dans le vecteur actuel après l'identification de l'élément par l'index spécifié.|  
|[Vector::ReplaceAll](#replaceall)|Supprime les éléments du Vector actif et les insère depuis le tableau spécifié.|  
|[Vector::RemoveAt](#removeat)|Supprime l'élément identifié par l'index spécifié à partir du Vector actif.|  
|[Vector::RemoveAtEnd](#removeatend)|Supprime l'élément à la fin du Vector actif.|  
|[Vector::SetAt](#setat)|Assigne la valeur spécifiée à l'élément du Vector actif identifié par l'index spécifié.|  
|[Vector::Size](#size)|Retourne le nombre d'éléments dans l'objet Vector actuel.|  
  
### <a name="events"></a>Événements  
  
|||  
|-|-|  
|Name|Description|  
|événement [Windows::Foundation::Collection::VectorChangedEventHandler\<T > ^ VectorChanged](http://go.microsoft.com/fwlink/p/?LinkId=262644)|Se produit lorsque le Vector est modifié.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 `Vector`  
  
### <a name="requirements"></a>Configuration requise  
 **En-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  

## <a name="append"></a>Vector::Append, méthode
Insère l'élément spécifié après le dernier élément du Vector actif.  
  
### <a name="syntax"></a>Syntaxe  
  
```    
virtual void Append(T item);  
```  
  
### <a name="parameters"></a>Paramètres  
 `index`  
 Élément à insérer dans le Vector. Le type de `item` est défini par le *T* typename.  
  


## <a name="clear"></a>Vector::Clear, méthode
Supprime tous les éléments du vecteur actuel.  
  
### <a name="syntax"></a>Syntaxe  
  
```    
virtual void Clear();  
```   


## <a name="first"></a>Vector::First (méthode)
Retourne un itérateur qui pointe vers le premier élément du Vector.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
  
virtual Windows::Foundation::Collections::IIterator <T>^ First();  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Itérateur qui pointe vers le premier élément du Vector.  
  
### <a name="remarks"></a>Notes  
 Un moyen pratique de contenir l’itérateur retourné par First() est d’assigner la valeur de retournée à une variable déclarée avec le **automatique** mot clé de déduction de type. Par exemple, `auto x = myVector->First();`. Cet itérateur connaît la longueur de la collection.  
  
 Lorsque vous avez besoin d’une paire d’itérateurs à passer à une fonction STL, utilisez les fonctions libres [Windows::Foundation :: Collections :: begin](../cppcx/begin-function.md) et [Windows::Foundation](../cppcx/end-function.md)  
  


## <a name="getat"></a>Vector::GetAt (méthode)
Récupère l'élément de l'objet Vector actuel qui est identifié par l'index spécifié.  
  
### <a name="syntax"></a>Syntaxe  
  
```    
virtual T GetAt(unsigned int index);  
```  
  
### <a name="parameters"></a>Paramètres  
 `index`  
 Entier non signé de base zéro qui spécifie un élément particulier dans l'objet Vector.  
  
### <a name="return-value"></a>Valeur de retour  
 Élément spécifié par le paramètre `index`. Le type d’élément est défini par le *T* typename.  
  


## <a name="getmany"></a>Vector::GetMany (méthode)
Récupère une séquence d'éléments du Vector actif en commençant à l'index spécifié et les copie dans le tableau alloué par l'appelant.  
  
### <a name="syntax"></a>Syntaxe  
  
```    
virtual unsigned int GetMany(
    unsigned int startIndex, 
    Platform::WriteOnlyArray<T>^ dest);  
```  
  
### <a name="parameters"></a>Paramètres  
 `startIndex`  
 L'index de base zéro du début des éléments à récupérer.  
  
 `dest`  
 Un tableau alloué par l'appelant des éléments qui commencent à l'élément spécifié par `startIndex` et se terminent au dernier élément du Vector.  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre d'éléments à récupérer.  
  
### <a name="remarks"></a>Notes  
 Cette fonction n'est pas destinée à être utilisée directement par le code client. Elle est utilisée en interne dans le [to_vector (fonction)](../cppcx/to-vector-function.md) pour permettre la conversion des instances Platform::Vector en instances std::vector.  
  


## <a name="getview"></a>Vector::GetView (méthode)
Retourne une vue en lecture seule d'un Vector, c'est-à-dire un IVectorView.  
  
### <a name="syntax"></a>Syntaxe  
  
```    
Windows::Foundation::Collections::IVectorView<T>^ GetView();  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Objet IVectorView.  
  


## <a name="indexof"></a>Vector::IndexOf (méthode)
Recherche l'élément spécifié dans l'objet Vector actuel, et s'il existe, retourne l'index de l'élément.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
  
virtual bool IndexOf(T value, unsigned int* index);  
```  
  
### <a name="parameters"></a>Paramètres  
 `value`  
 Élément à rechercher.  
  
 `index`  
 Index de base zéro de l'élément si le paramètre `value` est détecté ; sinon, 0.  
  
 Le paramètre `index` est égal à 0 si l'élément est le premier élément du vecteur ou que l'élément est introuvable. Si la valeur de retour est `true`, l'élément est trouvé et représente le premier élément ; sinon, l'élément est introuvable.  
  
### <a name="return-value"></a>Valeur de retour  
 `true` si l'élément spécifié est trouvé ; sinon, `false`.  
  
### <a name="remarks"></a>Notes  
 IndexOf uses std::find_if pour trouver l'élément. Les types d'élément personnalisés doivent surcharger les opérateurs == et != afin d'autoriser les comparaisons d'égalité requises par find_if.  
  


##  <a name="insertat"></a>Vector::InsertAt, méthode
Insère l'élément spécifié dans le vecteur actuel après l'identification de l'élément par l'index spécifié.  
  
### <a name="syntax"></a>Syntaxe  
  
```    
virtual void InsertAt(unsigned int index, T item)  
```  
  
### <a name="parameters"></a>Paramètres  
 `index`  
 Entier non signé de base zéro qui spécifie un élément particulier dans l'objet Vector.  
  
 `item`  
 Élément à insérer dans l'objet Vector après l'élément spécifié par `index`. Le type de `item` est défini par le *T* typename.  
  


## <a name="removeat"></a>Vector::RemoveAt, méthode
Supprime l'élément identifié par l'index spécifié à partir du Vector actif.  
  
### <a name="syntax"></a>Syntaxe  
  
```    
virtual void RemoveAt(unsigned int index);  
```  
  
### <a name="parameters"></a>Paramètres  
 `index`  
 Entier non signé de base zéro qui spécifie un élément particulier dans l'objet Vector.  
  


## <a name="removeatend"></a>Vector::removeatend, méthode
Supprime l'élément à la fin du Vector actif.  
  
### <a name="syntax"></a>Syntaxe  
  
```    
virtual void RemoveAtEnd();  
```  
  


## <a name="replaceall"></a>Vector::ReplaceAll, méthode
Supprime les éléments du Vector actif et les insère depuis le tableau spécifié.  
  
### <a name="syntax"></a>Syntaxe  
  
```    
virtual void ReplaceAll(const ::Platform::Array<T>^ arr);  
```  
  
### <a name="parameters"></a>Paramètres  
 `arr`  
 Un tableau d’objets dont le type est défini par le *T* typename.  
  


## <a name="setat"></a>Vector::SetAt, méthode
Assigne la valeur spécifiée à l'élément du Vector actif identifié par l'index spécifié.  
  
### <a name="syntax"></a>Syntaxe  
  
```    
virtual void SetAt(unsigned int index, T item);  
```  
  
### <a name="parameters"></a>Paramètres  
 `index`  
 Entier non signé de base zéro qui spécifie un élément particulier dans l'objet Vector.  
  
 `item`  
 Valeur à assigner à l’élément spécifié. Le type de `item` est défini par le *T* typename.  
  


## <a name="size"></a>Vector::Size, méthode
Retourne le nombre d'éléments dans l'objet Vector actuel.  
  
### <a name="syntax"></a>Syntaxe  
  
```    
virtual property unsigned int Size;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Nombre d’éléments dans l’objet Vector actuel.  
  


## <a name="ctor"></a>Vector::Vector (constructeur)
Initialise une nouvelle instance de la classe Vector.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
Vector();  
  
explicit Vector(unsigned int size);  
Vector( unsigned int size, T value);    
template <typename U> explicit Vector( const ::std::vector<U>& v);    
template <typename U> explicit Vector( std::vector<U>&& v);    

Vector( const T * ptr, unsigned int size);    
template <size_t N> explicit Vector(const T(&arr)[N]);    
template <size_t N> explicit Vector(const std::array<T, N>& a);   
explicit Vector(const Array<T>^ arr);  
  
template <typename InIt> Vector(InIt first, InIt last);   
Vector(std::initializer_list<T> il);  
```  
  
### <a name="parameters"></a>Paramètres  
 a  
 A [std::array](../standard-library/array-class-stl.md) qui sera utilisé pour initialiser le Vector.  
  
 a  
 A [Platform::Array](../cppcx/platform-array-class.md) qui sera utilisé pour initialiser le Vector.  
  
 `InIt`  
 Type d’une collection d’objets utilisée pour initialiser l’objet Vector actuel.  
  
 il  
 A [std::initializer_list](../standard-library/initializer-list-class.md) d’objets de type `T` qui sera utilisé pour initialiser le Vector.  
  
 `N`  
 Nombre d’éléments d’une collection d’objets utilisée pour initialiser l’objet Vector actuel.  
  
 `size`  
 Nombre d'éléments dans l'objet Vector.  
  
 `value`  
 Valeur utilisée pour initialiser chaque élément de l'objet Vector actuel.  
  
 `v`  
 Un [Lvalues et Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md) à un [std::vector](../standard-library/vector-class.md) qui est utilisé pour initialiser l’objet Vector actuel.  
  
 `ptr`  
 Pointeur vers un `std::vector` utilisé pour initialiser l'objet Vector actuel.  
  
 `arr`  
 A [Platform::Array](../cppcx/platform-array-class.md) objet qui est utilisé pour initialiser l’objet Vector actuel.  
  
 `a`  
 A [std::array](../standard-library/array-class-stl.md) objet qui est utilisé pour initialiser l’objet Vector actuel.  
  
 `first`  
 Premier élément d'une séquence d'objets utilisée pour initialiser l'objet Vector actuel. Le type de `first` est passé à l’aide de *un transfert parfait*. Pour plus d'informations, consultez [Déclarateur de référence rvalue : &&](../cpp/rvalue-reference-declarator-amp-amp.md).  
  
 `last`  
 Dernier élément d'une séquence d'objets utilisée pour initialiser l'objet Vector actuel. Le type de `last` est passé à l’aide de *un transfert parfait*. Pour plus d'informations, consultez [Déclarateur de référence rvalue : &&](../cpp/rvalue-reference-declarator-amp-amp.md).  
  


  
## <a name="see-also"></a>Voir aussi  
 [Plateforme Namespace](platform-namespace-c-cx.md)   
 [Création de composants Windows Runtime en C++](/MicrosoftDocs/windows-uwp/blob/docs/windows-apps-src/winrt-components/creating-windows-runtime-components-in-cpp.md)
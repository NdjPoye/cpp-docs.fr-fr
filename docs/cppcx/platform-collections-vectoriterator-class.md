---
title: 'Classe Platform::Collections :: vectoriterator | Documents Microsoft'
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::VectorIterator::VectorIterator
dev_langs:
- C++
helpviewer_keywords:
- VectorIterator Class
ms.assetid: d531cb42-27e0-48a6-bf5e-c265891a18ff
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: deaab183a092a073c6681004654312485959e924
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="platformcollectionsvectoriterator-class"></a>Platform::Collections::VectorIterator, classe
Fournit un itérateur Standard Template Library pour les objets dérivés de l’interface Windows Runtime IVector.  
  
 VectorIterator est un itérateur de proxy qui stocke des éléments de type VectorProxy\<T >. Toutefois, l'objet proxy n'est presque jamais visible par le code utilisateur. Pour plus d'informations, consultez [Collections (C++/CX)](../cppcx/collections-c-cx.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <typename T>  
class VectorIterator;  
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Nom de type de la classe de modèle VectorIterator.  
  
### <a name="members"></a>Membres  
  
### <a name="public-typedefs"></a>Typedefs publics  
  
|Nom|Description|  
|----------|-----------------|  
|`difference_type`|Différence de pointeur (ptrdiff_t).|  
|`iterator_category`|Catégorie d'un itérateur à accès aléatoire (::std::random_access_iterator_tag).|  
|`pointer`|Un pointeur vers un type interne Platform::Collections::Details::VectorProxy\<T >, qui est requis pour l’implémentation de VectorIterator.|  
|`reference`|Une référence à un type interne Platform::Collections::Details::VectorProxy\<T >, qui est requis pour l’implémentation de VectorIterator.|  
|`value_type`|Nom de type `T` .|  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[VectorIterator::VectorIterator](#ctor)|Initialise une nouvelle instance de la classe VectorIterator.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[VectorIterator::operator-, opérateur](#operator-minus)|Soustrait un nombre spécifié d'éléments de l'itérateur actuel en cédant un nouvel itérateur, ou un itérateur spécifié de l'itérateur actuel en cédant le nombre d'éléments entre les itérateurs.|  
|[VectorIterator::operator--, opérateur](#operator-decrement)|Décrémente le VectorIterator actif.|  
|[VectorIterator::operator!=, opérateur](#operator-inequality)|Indique si le VectorIterator actif n'est pas égal à un VectorIterator spécifié.|  
|[VectorIterator::operator*, opérateur](#operator-dereference)|Récupère une référence à l'élément spécifié par le VectorIterator actif.|  
|[VectorIterator::operator\[\]](#operator-at)|Récupère une référence à l'élément qui est un décalage spécifié à partir de l'objet VectorIterator actuel.|  
|[VectorIterator::operator+, opérateur](#operator-plus)|Retourne un VectorIterator qui référence l'élément spécifié au décalage spécifié à partir du VectorIterator spécifié.|  
|[VectorIterator::operator++, opérateur](#operator-increment)|Incrémente le VectorIterator actif.|  
|[VectorIterator::operator+=, opérateur](#operator-plus-assign)|Incrémente le VectorIterator actif du décalage spécifié.|  
|[VectorIterator::operator<, opérateur](#operator-less-than)|Indique si le VectorIterator actuel est inférieur au VectorIterator spécifié.|  
|[VectorIterator::operator\<= (opérateur)](#operator-less-than-or-equals)|Indique si l'objet VectorIterator actuel est inférieur ou égal à un objet VectorIterator spécifié.|  
|[VectorIterator::operator-=, opérateur](#operator-subtract-assign)|Décrémente l'objet VectorIterator actuel du décalage spécifié.|  
|[VectorIterator::operator==, opérateur](#operator-equality)|Indique si l'objet VectorIterator actuel est égal à un objet VectorIterator spécifié.|  
|[VectorIterator::operator>, opérateur](#operator-greater-than)|Indique si le VectorIterator actif est supérieur au VectorIterator spécifié.|  
|[VectorIterator::operator->, opérateur](#operator-arrow)|Récupère l'adresse de l'élément référencé par le VectorIterator actif.|  
|[VectorIterator::operator>=, opérateur](#operator-greater-than-or-equal)|Indique si le VectorIterator actif est supérieur ou égal à un VectorIterator spécifié.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 `VectorIterator`  
  
### <a name="requirements"></a>Spécifications  
 **En-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  

## <a name="operator-arrow"></a>  VectorIterator::operator -&gt; (opérateur)
Récupère l'adresse de l'élément référencé par le VectorIterator actif.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
Detail::ArrowProxy<T> operator->() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur de l’élément référencé par le VectorIterator actif.  
  
 Le type de la valeur de retour est un type interne non spécifié nécessaire pour l’implémentation de cet opérateur.  
  


## <a name="operator-decrement"></a>  VectorIterator::operator--(opérateur)
Décrémente le VectorIterator actif.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
  
VectorIterator& operator--();  
VectorIterator operator--(int);  
```  
  
### <a name="return-value"></a>Valeur de retour  
 La première syntaxe décrémente le VectorIterator actif puis le retourne. La deuxième syntaxe retourne une copie du VectorIterator actif puis décrémente le VectorIterator actif.  
  
### <a name="remarks"></a>Notes  
 La première syntaxe VectorIterator prédécrémente le VectorIterator actif.  
  
 La deuxième syntaxe post-décrémente le VectorIterator actif. Le `int` type dans la deuxième syntaxe indique une opération de post-décrémentation, pas un opérande entier réel.  
  


## <a name="operator-dereference"></a>  Opérateur de VectorIterator::operator
Récupère l’adresse de l’élément spécifié par le VectorIterator actif.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
reference operator*() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Élément spécifié par le VectorIterator actif.  
  


## <a name="operator-equality"></a>  VectorIterator::operator == (opérateur)
Indique si l'objet VectorIterator actuel est égal à un objet VectorIterator spécifié.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
bool operator==(const VectorIterator& other) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `other`  
 Autre objet VectorIterator.  
  
### <a name="return-value"></a>Valeur de retour  
 `true` si l'objet VectorIterator actuel est égal à `other` ; sinon, `false`.  
  


## <a name="operator-greater-than"></a>  VectorIterator::operator&gt; (opérateur)
Indique si le VectorIterator actif est supérieur au VectorIterator spécifié.  
  
### <a name="syntax"></a>Syntaxe  
  
```cpp  
  
bool operator>(const VectorIterator& other) const   
```  
  
### <a name="parameters"></a>Paramètres  
 `other`  
 Autre objet VectorIterator.  
  
### <a name="return-value"></a>Valeur de retour  
 `true` Si le VectorIterator actif est supérieur à `other`; sinon, `false`.  
  


## <a name="operator-greater-than-or-equals"></a>  VectorIterator::operator&gt;= (opérateur)
Indique si le VectorIterator actif est supérieur ou égal au VectorIterator spécifié.  
  
### <a name="syntax"></a>Syntaxe  
  
```cpp  
  
bool operator>=(const VectorIterator& other) const   
```  
  
### <a name="parameters"></a>Paramètres  
 `other`  
 Autre objet VectorIterator.  
  
### <a name="return-value"></a>Valeur de retour  
 `true` si le VectorIterator actif est supérieur ou égal à `other` ; sinon, `false`.    


## <a name="operator-increment"></a>  VectorIterator::operator ++ (opérateur)
Incrémente le VectorIterator actif.  
  
### <a name="syntax"></a>Syntaxe  
  
```    
VectorIterator& operator++();  
VectorIterator operator++(int);  
```  
  
### <a name="return-value"></a>Valeur de retour  
 La première syntaxe incrémente le VectorIterator actif puis le retourne. La deuxième syntaxe retourne une copie du VectorIterator actif puis incrémente le VectorIterator actif.  
  
### <a name="remarks"></a>Notes  
 La première syntaxe VectorIterator préincrémente le VectorIterator actif.  
  
 La deuxième syntaxe postincrémente le VectorIterator actif. Le type `int` dans la deuxième syntaxe n'indique pas un opérande entier réel mais une post-incrémentation.  
  


## <a name="operator-inequality"></a>  VectorIterator::operator ! =, opérateur
Indique si le VectorIterator actif n'est pas égal à un VectorIterator spécifié.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
bool operator!=(const VectorIterator& other) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `other`  
 Autre objet VectorIterator.  
  
### <a name="return-value"></a>Valeur de retour  
 `true` Si le VectorIterator actif n’est pas égal à `other`; sinon, `false`.  
  


## <a name="operator-less-than"></a>  VectorIterator::operator&lt; (opérateur)
Indique si le VectorIterator actuel est inférieur au VectorIterator spécifié.  
  
### <a name="syntax"></a>Syntaxe  
  
```cpp  
  
bool operator<(const VectorIterator& other) const   
```  
  
### <a name="parameters"></a>Paramètres  
 `other`  
 Autre objet VectorIterator.  
  
### <a name="return-value"></a>Valeur de retour  
 `true` si le VectorIterator actuel est inférieur à `other` ; sinon, `false`.  
  


## <a name="operator-less-than-or-equals"></a>  VectorIterator::operator&lt;= (opérateur)
Indique si l'objet VectorIterator actuel est inférieur ou égal à un objet VectorIterator spécifié.  
  
### <a name="syntax"></a>Syntaxe  
  
```cpp  
  
bool operator<=(const VectorIterator& other) const   
```  
  
### <a name="parameters"></a>Paramètres  
 `other`  
 Autre objet VectorIterator.  
  
### <a name="return-value"></a>Valeur de retour  
 `true` Si le VectorIterator actif est inférieur ou égal à `other`; sinon, `false`.  
  


## <a name="operator-minus"></a>  VectorIterator::operator-(opérateur)
Soustrait un nombre spécifié d'éléments de l'itérateur actuel en cédant un nouvel itérateur, ou un itérateur spécifié de l'itérateur actuel en cédant le nombre d'éléments entre les itérateurs.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
  
VectorIterator operator-(difference_type n) const;  
  
difference_type operator-(const VectorIterator& other) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `n`  
 Nombre d'éléments.  
  
 `other`  
 Autre objet VectorIterator.  
  
### <a name="return-value"></a>Valeur de retour  
 La première syntaxe d’opérateur retourne un objet VectorIterator `n` éléments inférieur à l’objet VectorIterator actuel. La deuxième syntaxe d’opérateur retourne le nombre d’éléments entre actuel et le `other` VectorIterator.  
  


## <a name="operator-plus-assign"></a>  VectorIterator::operator += (opérateur)
Incrémente le VectorIterator actif du décalage spécifié.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
VectorIterator& operator+=(difference_type n);  
```  
  
### <a name="parameters"></a>Paramètres  
 `n`  
 Déplacement d'un entier.  
  
### <a name="return-value"></a>Valeur de retour  
 Objet VectorIterator mis à jour.  
  


## <a name="operator-plus"></a>  ectorIterator::operator +, opérateur
Retourne un VectorIterator qui référence l'élément spécifié au décalage spécifié à partir du VectorIterator spécifié.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
  
VectorIterator operator+(difference_type n);  
  
template <typename T>  
inline VectorIterator<T> operator+(
  ptrdiff_t n, 
  const VectorIterator<T>& i);  
  
```  
  
### <a name="parameters"></a>Paramètres  
 `T`  
 Dans la deuxième syntaxe, typename du VectorIterator.  
  
 `n`  
 Déplacement d'un entier.  
  
 `i`  
 Dans la deuxième syntaxe, un VectorIterator.  
  
### <a name="return-value"></a>Valeur de retour  
 Dans la première syntaxe, VectorIterator qui référence l'élément spécifié au décalage spécifié à partir du VectorIterator actuel.  
  
 Dans la deuxième syntaxe, VectorIterator qui référence l'élément au décalage spécifié à partir du début du paramètre `i`.  
  
### <a name="remarks"></a>Notes  
 Exemple pour la première syntaxe  
  


## <a name="operator-minus-equals"></a>  VectorIterator::operator-= (opérateur)
Décrémente l'objet VectorIterator actuel du décalage spécifié.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
VectorIterator& operator-=(difference_type n);  
```  
  
### <a name="parameters"></a>Paramètres  
 `n`  
 Déplacement d'un entier.  
  
### <a name="return-value"></a>Valeur de retour  
 Objet VectorIterator mis à jour.  
  


## <a name="operator-at"></a>  VectorIterator::operator\[\]
Récupère une référence à l'élément qui est un décalage spécifié à partir de l'objet VectorIterator actuel.  
  
### <a name="syntax"></a>Syntaxe  
  
```    
reference operator[](difference_type n) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `n`  
 Déplacement d'un entier.  
  
### <a name="return-value"></a>Valeur de retour  
 Élément qui est décalé par les éléments `n` à partir du VectorIterator actif.  
  


## <a name="ctor"></a>  VectorIterator::VectorIterator (constructeur)
Initialise une nouvelle instance de la classe VectorIterator.  
  
### <a name="syntax"></a>Syntaxe  
  
```    
VectorIterator();  
  
explicit VectorIterator(  
   Windows::Foundation::Collections::IVector<T>^ v);  
```  
  
### <a name="parameters"></a>Paramètres  
 `v`  
 Un IVector\<T > objet.  
  
### <a name="remarks"></a>Notes  
 Le premier exemple de syntaxe est le constructeur par défaut. Le deuxième exemple de syntaxe est un constructeur explicite qui est utilisé pour construire un VectorIterator à partir d’un IVector\<T > objet.  
  


  
## <a name="see-also"></a>Voir aussi  
 [Plateforme Namespace](platform-namespace-c-cx.md)
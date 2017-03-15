---
title: duration, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- chrono/std::chrono::duration
dev_langs:
- C++
ms.assetid: 06b863b3-65be-4ded-a72e-6e1eb1531077
caps.latest.revision: 10
author: corob-msft
ms.author: corob
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 843e4954b3a5b20d504dd5c8bf582dc56d4cbcbd
ms.lasthandoff: 02/24/2017

---
# <a name="duration-class"></a>duration, classe
Décrit un type contenant un *intervalle de temps*, qui est le temps écoulé entre deux points dans le temps.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <class Rep, class Period = ratio<1>>  
class duration;  
template <class Rep, class Period>  
class duration;  
template <class Rep, class Period1, class Period2>  
class duration <duration<Rep, Period1>, Period2>;  
```  
  
## <a name="remarks"></a>Notes  
 L’argument de modèle `Rep` décrit le type utilisé pour contenir le nombre de battements d’horloge dans l’intervalle. L’argument de modèle `Period` est une instanciation du [rapport](../standard-library/ratio.md) qui décrit la taille de l’intervalle représenté par chaque battement.  
  
## <a name="members"></a>Membres  
  
### <a name="public-typedefs"></a>Typedefs publics  
  
|Nom|Description|  
|----------|-----------------|  
|duration::period, typedef|Représente un synonyme du paramètre de modèle `Period`.|  
|duration::rep, typedef|Représente un synonyme du paramètre de modèle `Rep`.|  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[duration::duration, constructeur](#duration__duration_constructor)|Construit un objet `duration`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[duration::count](#duration__count_method)|Retourne le nombre de battements d’horloge dans l’intervalle de temps.|  
|[duration::max](#duration__max_method)|Static. Retourne la valeur maximale autorisée du paramètre de modèle `Ref`.|  
|[duration::min](#duration__min_method)|Static. Retourne la valeur minimale autorisée du paramètre de modèle `Ref`.|  
|[duration::zero](#duration__zero_method)|Static. Retourne `Rep`(0).|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[duration::operator-](#duration__operator-)|Retourne une copie de l’objet `duration` avec un nombre de battements négatifs.|  
|[duration::operator--](#duration__operator--)|Décrémente le nombre de battements stocké.|  
|[duration::operator=](#duration__operator_eq)|Réduit le nombre de battements stocké modulo une valeur spécifiée.|  
|[duration::operator*=](#duration__operator_star_eq)|Multiplie le nombre de battements stocké par une valeur spécifiée.|  
|[duration::operator/=](#duration__operator__eq)|Divise le nombre de battements stocké par le nombre de battements d’un objet `duration` spécifié.|  
|[duration::operator+](#duration__operator_add)|Retourne `*this`.|  
|[duration::operator++](#duration__operator_add_add)|Incrémente le nombre de battements stocké.|  
|[duration::operator+=](#duration__operator_add_eq)|Ajoute le nombre de battements d’un objet `duration` spécifié au nombre de battements stocké.|  
|[duration::operator-=](#duration__operator-_eq)|Soustrait le nombre de battements d’un objet `duration` spécifié du nombre de battements stocké.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** chrono  
  
 **Espace de noms :** std::chrono  
  
##  <a name="a-namedurationcountmethoda--durationcount"></a><a name="duration__count_method"></a>  duration::count  
 Récupère le nombre de battements d'horloge dans l'intervalle de temps.  
  
```  
constexpr Rep count() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Nombre de battements d'horloge dans l'intervalle de temps.  
  
##  <a name="a-namedurationdurationconstructora--durationduration-constructor"></a><a name="duration__duration_constructor"></a>  duration::duration, constructeur  
 Construit un objet `duration`.  
  
```  
constexpr duration() = default;  
 
template <class Rep2>  
constexpr explicit duration(const Rep2& R);

 
template <class Rep2, class Period2>  
constexpr duration(const duration<Rep2, Period2>& Dur);
```  
  
### <a name="parameters"></a>Paramètres  
 `Rep2`  
 Type arithmétique pour représenter le nombre de battements.  
  
 `Period2`  
 Spécialisation de modèle `std::ratio` pour représenter la période de battements en unités de secondes.  
  
 `R`  
 Nombre de battements de la période par défaut.  
  
 `Dur`  
 Nombre de battements de la période spécifiée par `Period2`.  
  
### <a name="remarks"></a>Notes  
 Le constructeur par défaut crée un objet qui n’est pas initialisé. L’initialisation de valeurs à l’aide d’accolades vides initialise un objet qui représente un intervalle de temps de zéro battement d’horloge.  
  
 Le deuxième constructeur à un argument de modèle construit un objet qui représente un intervalle de temps de `R` battements d’horloge à l’aide de la période par défaut `std::ratio<1>`. Pour éviter l'arrondi des nombres de battements, il ne faut pas construire un objet de durée à partir d'un type de représentation `Rep2` qui peut être traité comme un type à virgule flottante quand `duration::rep` ne peut pas être traité comme un type à virgule flottante.  
  
 Le troisième constructeur à deux arguments de modèle construit un objet qui représente un intervalle de temps dont la longueur est l’intervalle de temps spécifié par `Dur`. Pour éviter la troncation du nombre de battements, il ne faut pas construire un objet de durée à partir d’un autre objet de durée dont le type est *incommensurable* avec le type cible.  
  
 Un type de durée `D1` est *incommensurable* avec un autre type de durée `D2` si `D2` ne peut pas être traité comme un type à virgule flottante et que [ratio_divide\<D1::period, D2::period>::type::den](../standard-library/ratio.md) n’est pas égal à 1.  
  
 À moins que `Rep2` ne soit implicitement convertible en `rep` et que `treat_as_floating_point<rep>`*contienne la valeur true* ou que `treat_as_floating_point<Rep2>`*contienne la valeur false*, le deuxième constructeur ne participe pas à la résolution de surcharge. Pour plus d’informations, consultez [<type_traits>](../standard-library/type-traits.md).  
  
 À moins qu’aucun dépassement ne soit induit dans la conversion et que `treat_as_floating_point<rep>`*contienne la valeur true*, ou que `ratio_divide<Period2, period>::den` soit égal à 1 et que `treat_as_floating_point<Rep2>`*contienne la valeur false*, le troisième constructeur ne participe pas à la résolution de surcharge. Pour plus d’informations, consultez [<type_traits>](../standard-library/type-traits.md).  
  
##  <a name="a-namedurationmaxmethoda--durationmax"></a><a name="duration__max_method"></a>  duration::max  
 Méthode statique qui retourne la limite supérieure des valeurs du type de paramètre de modèle `Ref`.  
  
```  
static constexpr duration max();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne `duration(duration_values<rep>::max())`.  
  
##  <a name="a-namedurationminmethoda--durationmin"></a><a name="duration__min_method"></a>  duration::min  
 Méthode statique qui retourne la limite inférieure des valeurs du type de paramètre de modèle `Ref`.  
  
```  
static constexpr duration min();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne `duration(duration_values<rep>::min())`.  
  
##  <a name="a-namedurationoperator-a--durationoperator-"></a><a name="duration__operator-"></a>  duration::operator-  
 Retourne une copie de l’objet `duration` avec un nombre de battements négatifs.  
  
```  
constexpr duration operator-() const;
```  
  
##  <a name="a-namedurationoperator--a--durationoperator--"></a><a name="duration__operator--"></a>  duration::operator--  
 Décrémente le nombre de battements stocké.  
  
```  
duration& operator--();

duration operator--(int);
```  
  
### <a name="return-value"></a>Valeur de retour  
 La première méthode retourne `*this`.  
  
 La deuxième méthode retourne une copie de `*this` effectuée avant la décrémentation.  
  
##  <a name="a-namedurationoperatoreqa--durationoperator"></a><a name="duration__operator_eq"></a>  duration::operator=  
 Réduit le nombre de battements stocké modulo une valeur spécifiée.  
  
```  
duration& operator%=(const rep& Div);

duration& operator%=(const duration& Div);
```  
  
### <a name="parameters"></a>Paramètres  
 `Div`  
 Pour la première méthode, `Div` représente un nombre de battements. Pour la deuxième méthode, `Div` est un objet `duration` qui contient un nombre de battements.  
  
### <a name="return-value"></a>Valeur de retour  
 Objet `duration` une fois l’opération modulo effectuée.  
  
##  <a name="a-namedurationoperatorstareqa--durationoperator"></a><a name="duration__operator_star_eq"></a>  duration::operator*=  
 Multiplie le nombre de battements stocké par une valeur spécifiée.  
  
```  
duration& operator*=(const rep& Mult);
```  
  
### <a name="parameters"></a>Paramètres  
 `Mult`  
 Valeur du type spécifié par `duration::rep`.  
  
### <a name="return-value"></a>Valeur de retour  
 Objet `duration` une fois la multiplication effectuée.  
  
##  <a name="a-namedurationoperatoreqa--durationoperator"></a><a name="duration__operator__eq"></a>  duration::operator/=  
 Divise le nombre de battements stocké par une valeur spécifiée.  
  
```  
duration& operator/=(const rep& Div);
```  
  
### <a name="parameters"></a>Paramètres  
 `Div`  
 Valeur du type spécifié par `duration::rep`.  
  
### <a name="return-value"></a>Valeur de retour  
 Objet `duration` une fois la division effectuée.  
  
##  <a name="a-namedurationoperatoradda--durationoperator"></a><a name="duration__operator_add"></a>  duration::operator+  
 Retourne `*this`.  
  
```  
constexpr duration operator+() const;
```  
  
##  <a name="a-namedurationoperatoraddadda--durationoperator"></a><a name="duration__operator_add_add"></a>  duration::operator++  
 Incrémente le nombre de battements stocké.  
  
```  
duration& operator++();

duration operator++(int);
```  
  
### <a name="return-value"></a>Valeur de retour  
 La première méthode retourne `*this`.  
  
 La deuxième méthode retourne une copie de `*this` effectuée avant l’incrémentation.  
  
##  <a name="a-namedurationoperatoraddeqa--durationoperator"></a><a name="duration__operator_add_eq"></a>  duration::operator+=  
 Ajoute le nombre de battements d’un objet `duration` spécifié au nombre de battements stocké.  
  
```  
duration& operator+=(const duration& Dur);
```  
  
### <a name="parameters"></a>Paramètres  
 `Dur`  
 Objet `duration`.  
  
### <a name="return-value"></a>Valeur de retour  
 Objet `duration` une fois l’addition effectuée.  
  
##  <a name="a-namedurationoperator-eqa--durationoperator-"></a><a name="duration__operator-_eq"></a>  duration::operator-=  
 Soustrait le nombre de battements d’un objet `duration` spécifié du nombre de battements stocké.  
  
```  
duration& operator-=(const duration& Dur);
```  
  
### <a name="parameters"></a>Paramètres  
 `Dur`  
 Objet `duration`.  
  
### <a name="return-value"></a>Valeur de retour  
 Objet `duration` une fois la soustraction effectuée.  
  
##  <a name="a-namedurationzeromethoda--durationzero"></a><a name="duration__zero_method"></a>  duration::zero  
 Retourne `duration(duration_values<rep>::zero())`.  
  
```  
static constexpr duration zero();
```  
  
##  <a name="a-namedurationoperatormodeqa--durationoperator-mod"></a><a name="duration__operator_mod_eq"></a>  duration::operator mod=  
 Réduit le nombre de cycles stocké modulo Div ou Div.count().  
  
```  
duration& operator%=(const rep& Div);duration& operator%=(const duration& Div);
```  
  
### <a name="parameters"></a>Paramètres  
 `Div`  
 Diviseur, qui est un objet duration ou une valeur représentant le nombre de cycles.  
  
### <a name="remarks"></a>Notes  
 La première fonction membre réduit le nombre de cycles stocké modulo Div et retourne *this. La deuxième fonction membre réduit le nombre de battements stocké modulo Div.count() et retourne \*this.  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur les fichiers d’en-tête](../standard-library/cpp-standard-library-header-files.md)   
 [\<chrono>](../standard-library/chrono.md)   
 [duration_values, structure](../standard-library/duration-values-structure.md)


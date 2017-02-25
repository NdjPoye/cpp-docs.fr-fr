---
title: "SafeInt, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "SafeInt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SafeInt (classe)"
ms.assetid: 27a8f087-2511-46f9-8d76-2aeb66ca272f
caps.latest.revision: 16
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 16
---
# SafeInt, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Étend les primitives d'entiers pour éviter un dépassement sur des entiers et vous permet de comparer différents types d'entiers.  
  
## Syntaxe  
  
```  
template<typename T, typename E = _SAFEINT_DEFAULT_ERROR_POLICY>  
class SafeInt;  
```  
  
#### Paramètres  
  
|Modèle|Description|  
|------------|-----------------|  
|T|Le type de paramètre booléen ou entier que `SafeInt` remplace.|  
|E|Un type de données énuméré qui définit la stratégie de gestion des erreurs.|  
|U|Le type de paramètre de type entier ou booléen pour l'opérande secondaire.|  
  
|Paramètre|Description|  
|---------------|-----------------|  
|\[in\] rhs|Un paramètre d'entrée qui représente la valeur à droite de l'opérateur dans plusieurs fonctions autonomes.|  
|\[in\] i|Un paramètre d'entrée qui représente la valeur à droite de l'opérateur dans plusieurs fonctions autonomes.|  
|\[in\] bits|Un paramètre d'entrée qui représente la valeur à droite de l'opérateur dans plusieurs fonctions autonomes.|  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[SafeInt::SafeInt](../windows/safeint-safeint.md)|Constructeur par défaut.|  
  
### Opérateurs d'assignation  
  
|Nom|Syntaxe|  
|---------|-------------|  
|\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator= (const U& rhs)`|  
|\=|`SafeInt<T,E>& operator= (const T& rhs) throw()`|  
|\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator= (const SafeInt<U, E>& rhs)`|  
|\=|`SafeInt<T,E>& operator= (const SafeInt<T,E>& rhs) throw()`|  
  
### Opérateurs de casting  
  
|Nom|Syntaxe|  
|---------|-------------|  
|bool|`operator bool() throw()`|  
|char|`operator char() const`|  
|signed char|`operator signed char() const`|  
|unsigned char|`operator unsigned char() const`|  
|\_\_int16|`operator __int16() const`|  
|unsigned \_\_int16|`operator unsigned __int16() const`|  
|\_\_int32|`operator __int32() const`|  
|unsigned \_\_int32|`operator unsigned __int32() const`|  
|long|`operator long() const`|  
|unsigned long|`operator unsigned long() const`|  
|\_\_int64|`operator __int64() const`|  
|unsigned \_\_int64|`operator unsigned __int64() const`|  
|wchar\_t|`operator wchar_t() const`|  
  
### Opérateurs de comparaison  
  
|Nom|Syntaxe|  
|---------|-------------|  
|\<|`template<typename U>`<br /><br /> `bool operator< (U rhs) const throw()`|  
|\<|`bool operator< (SafeInt<T,E> rhs) const throw()`|  
|\>\=|`template<typename U>`<br /><br /> `bool operator>= (U rhs) const throw()`|  
|\>\=|`Bool operator>= (SafeInt<T,E> rhs) const throw()`|  
|\>|`template<typename U>`<br /><br /> `bool operator> (U rhs) const throw()`|  
|\>|`Bool operator> (SafeInt<T,E> rhs) const throw()`|  
|\<\=|`template<typename U>`<br /><br /> `bool operator<= (U rhs) const throw()`|  
|\<\=|`bool operator<= (SafeInt<T,E> rhs) const throw()`|  
|\=\=|`template<typename U>`<br /><br /> `bool operator== (U rhs) const throw()`|  
|\=\=|`bool operator== (bool rhs) const throw()`|  
|\=\=|`bool operator== (SafeInt<T,E> rhs) const throw()`|  
|\!\=|`template<typename U>`<br /><br /> `bool operator!= (U rhs) const throw()`|  
|\!\=|`bool operator!= (bool b) const throw()`|  
|\!\=|`bool operator!= (SafeInt<T,E> rhs) const throw()`|  
  
### Opérateurs arithmétiques  
  
|Nom|Syntaxe|  
|---------|-------------|  
|\+|`const SafeInt<T,E>& operator+ () const throw()`|  
|\-|`SafeInt<T,E> operator- () const`|  
|\+\+|`SafeInt<T,E>& operator++ ()`|  
|\-\-|`SafeInt<T,E>& operator-- ()`|  
|%|`template<typename U>`<br /><br /> `SafeInt<T,E> operator% (U rhs) const`|  
|%|`SafeInt<T,E> operator% (SafeInt<T,E> rhs) const`|  
|%\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator%= (U rhs)`|  
|%\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator%= (SafeInt<U, E> rhs)`|  
|\*|`template<typename U>`<br /><br /> `SafeInt<T,E> operator* (U rhs) const`|  
|\*|`SafeInt<T,E> operator* (SafeInt<T,E> rhs) const`|  
|\*\=|`SafeInt<T,E>& operator*= (SafeInt<T,E> rhs)`|  
|\*\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator*= (U rhs)`|  
|\*\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator*= (SafeInt<U, E> rhs)`|  
|\/|`template<typename U>`<br /><br /> `SafeInt<T,E> operator/ (U rhs) const`|  
|\/|`SafeInt<T,E> operator/ (SafeInt<T,E> rhs ) const`|  
|\/\=|`SafeInt<T,E>& operator/= (SafeInt<T,E> i)`|  
|\/\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator/= (U i)`|  
|\/\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator/= (SafeInt<U, E> i)`|  
|\+|`SafeInt<T,E> operator+ (SafeInt<T,E> rhs) const`|  
|\+|`template<typename U>`<br /><br /> `SafeInt<T,E> operator+ (U rhs) const`|  
|\+\=|`SafeInt<T,E>& operator+= (SafeInt<T,E> rhs)`|  
|\+\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator+= (U rhs)`|  
|\+\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator+= (SafeInt<U, E> rhs)`|  
|\-|`template<typename U>`<br /><br /> `SafeInt<T,E> operator- (U rhs) const`|  
|\-|`SafeInt<T,E> operator- (SafeInt<T,E> rhs) const`|  
|\-\=|`SafeInt<T,E>& operator-= (SafeInt<T,E> rhs)`|  
|\-\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator-= (U rhs)`|  
|\-\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator-= (SafeInt<U, E> rhs)`|  
  
### Opérateurs logiques  
  
|Nom|Syntaxe|  
|---------|-------------|  
|\!|`bool operator !() const throw()`|  
|~|`SafeInt<T,E> operator~ () const throw()`|  
|\<\<|`template<typename U>`<br /><br /> `SafeInt<T,E> operator<< (U bits) const throw()`|  
|\<\<|`template<typename U>`<br /><br /> `SafeInt<T,E> operator<< (SafeInt<U, E> bits) const throw()`|  
|\<\<\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator<<= (U bits) throw()`|  
|\<\<\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator<<= (SafeInt<U, E> bits) throw()`|  
|\>\>|`template<typename U>`<br /><br /> `SafeInt<T,E> operator>> (U bits) const throw()`|  
|\>\>|`template<typename U>`<br /><br /> `SafeInt<T,E> operator>> (SafeInt<U, E> bits) const throw()`|  
|\>\>\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator>>= (U bits) throw()`|  
|\>\>\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator>>= (SafeInt<U, E> bits) throw()`|  
|&|`SafeInt<T,E> operator& (SafeInt<T,E> rhs) const throw()`|  
|&|`template<typename U>`<br /><br /> `SafeInt<T,E> operator& (U rhs) const throw()`|  
|&\=|`SafeInt<T,E>& operator&= (SafeInt<T,E> rhs) throw()`|  
|&\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator&= (U rhs) throw()`|  
|&\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator&= (SafeInt<U, E> rhs) throw()`|  
|^|`SafeInt<T,E> operator^ (SafeInt<T,E> rhs) const throw()`|  
|^|`template<typename U>`<br /><br /> `SafeInt<T,E> operator^ (U rhs) const throw()`|  
|^\=|`SafeInt<T,E>& operator^= (SafeInt<T,E> rhs) throw()`|  
|^\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator^= (U rhs) throw()`|  
|^\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator^= (SafeInt<U, E> rhs) throw()`|  
|&#124;|`SafeInt<T,E> operator&#124; (SafeInt<T,E> rhs) const throw()`|  
|&#124;|`template<typename U>`<br /><br /> `SafeInt<T,E> operator&#124; (U rhs) const throw()`|  
|&#124;\=|`SafeInt<T,E>& operator&#124;= (SafeInt<T,E> rhs) throw()`|  
|&#124;\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator&#124;= (U rhs) throw()`|  
|&#124;\=|`template<typename U>`<br /><br /> `SafeInt<T,E>& operator&#124;= (SafeInt<U, E> rhs) throw()`|  
  
## Notes  
 La classe d' `SafeInt` protège contre le dépassement sur des entiers dans des opérations mathématiques.  Par exemple, envisagez d'ajouter deux entiers de 8 bits: l'un a la valeur 200 et le second a la valeur 100.  L'opération mathématique correcte est 200 \+ 100 \= 300.  Cependant, du fait de la limite entière de 8 bits, le bit supérieur est perdu et le compilateur retourne 44 \(300 \- 2<sup>8</sup>\) comme résultat.  Toute opération qui dépend de cette équation mathématique génère un comportement inattendu.  
  
 La classe d' `SafeInt` vérifie si un dépassement de capacité arithmétique a lieu ou si le code tente de diviser par zéro.  Dans les deux cas, la classe appelle le gestionnaire d'erreurs pour informer le programme du problème potentiel.  
  
 Cette classe vous permet également de comparer deux types différents d'entiers tant que ce sont des objets d' `SafeInt`.  En règle générale, lorsque vous exécutez une comparaison, vous devez d'abord convertir les nombres pour qu'ils soient du même type.  La conversion d'un nombre à un autre type requiert souvent des contrôles pour garantir qu'aucune perte de données n'a lieu.  
  
 Le tableau des opérateurs dans ce thème répertorie les fonctions mathématiques et les opérateurs de comparaison pris en charge par la classe d' `SafeInt` .  La plupart des opérateurs mathématiques retournent un objet d' `SafeInt` de type `T`.  
  
 Les opérations de comparaison entre un `SafeInt` et un type intégral peuvent être effectuées dans un sens ou l'autre.  Par exemple, `SafeInt<int>(x) < y` et `y > SafeInt<int>(x)` sont valides et retournent le même résultat.  
  
 De nombreux opérateurs binaires ne prennent pas en charge l'utilisation de deux types différents d' `SafeInt`.  Un exemple de cette opération est l'opérateur d' `&`.  `SafeInt<T, E> & int` est pris en charge, mais `SafeInt<T, E> & SafeInt<U, E>` ne l'est pas.  Dans le dernier exemple, le compilateur ne connaît pas le type de paramètre à retourner.  Une solution à ce problème consiste à convertir le deuxième paramètre vers le type de base.  En utilisant les mêmes paramètres, cette opération peut être effectuée avec `SafeInt<T, E> & (U)SafeInt<U, E>`.  
  
> [!NOTE]
>  Pour toutes les opérations de bits, les deux paramètres différents doivent avoir la même taille.  Si les tailles diffèrent, le compilateur lève une exception d' [ASSERT](../Topic/ASSERT%20\(MFC\).md).  La précision des résultats de cette opération ne peuvent pas être garantis.  Pour résoudre ce problème, effectuez un cast de la valeur la plus petite jusqu'à ce qu'elle soit de la même taille que le paramètre le plus grand.  
  
 Pour les opérateurs de décalage, le déplacement de plus de bits que ceux qui existent pour le type de modèle lèvera une exception d'ASSERTION.  Cela n'a aucun effet dans le mode de version.  Combiner deux types de paramètres de SafeInt est possible pour les opérateurs de décalage car le type de retour est identique au type d'origine.  Le numéro à droite de l'opérateur indique uniquement le nombre de bits à déplacer.  
  
 Lorsque vous exécutez une comparaison logique avec un objet de SafeInt, la comparaison est strictement arithmétique.  Par exemple, considérez ces expressions:  
  
-   `SafeInt<uint>((uint)~0) > -1`  
  
-   `((uint)~0) > -1`  
  
 La première déclaration se résoud à `true`, mais la deuxième déclaration se résoud à `false`.  La négation au niveau du bit à 0 est 0xFFFFFFFF.  Dans la deuxième déclaration, l'opérateur de comparaison par défaut compare 0xFFFFFFFF à 0xFFFFFFFF et les considère égaux.  L'opérateur de comparaison pour la classe d' `SafeInt` vous signale que le deuxième paramètre est négatif alors que le premier paramètre n'est pas signé.  Par conséquent, même si la représentation binaire est identique, l'opérateur logique d' `SafeInt` se rend compte que l'entier non signé est supérieur à \-1.  
  
 Soyez prudent lorsque vous utilisez la classe d' `SafeInt` avec l'opérateur ternaire d' `?:`.  Observons la ligne de code suivante:  
  
```  
Int x = flag ? SafeInt<unsigned int>(y) : -1;  
```  
  
 Le compilateur le convertit vers ceci:  
  
```  
Int x = flag ? SafeInt<unsigned int>(y) : SafeInt<unsigned int>(-1);  
```  
  
 Si `flag` est `false`, le compilateur lève une exception au lieu d'affecter la valeur \-1 à `x`.  Par conséquent, pour éviter ce comportement, le code approprié à utiliser est la ligne suivante.  
  
```  
Int x = flag ? (int) SafeInt<unsigned int>(y) : -1;  
```  
  
 `T` et `U` peuvent être attribués un type booléen, un type caractère, ou un type entier.  Les types d'entiers peuvent être signés ou non signés et de toute taille entre 8 bits et 64 bits.  
  
> [!NOTE]
>  Bien que la classe d' `SafeInt` reçoive n'importe quel type d'entier, elle marche plus efficacement avec les types non signés.  
  
 `E` est le mécanisme de gestion des erreurs qu' `SafeInt` utilise.  Deux mécanismes de gestion des erreurs sont fournis avec la bibliothèque de SafeInt.  La stratégie par défaut est `SafeIntErrorPolicy_SafeIntException`, qui lève une exception de [SafeIntException, classe](../windows/safeintexception-class.md) lorsqu'une erreur se produit.  L'autre stratégie est `SafeIntErrorPolicy_InvalidParameter`, qui arrête le programme si une erreur se produit.  
  
 Il existe deux options pour personnaliser la stratégie d'erreur.  La première option consiste à définir le paramètre `E` lorsque vous créez un `SafeInt`.  Utilisez cette option lorsque vous souhaitez modifier la stratégie de gestion des erreurs pour un seul `SafeInt`.  L'autre solution consiste à définir `_SAFEINT_DEFAULT_ERROR_POLICY` comme votre programme personnalisé de gestion des erreurs avant d'inclure la bibliothèque d' `SafeInt`.  Utilisez cette option si vous souhaitez modifier la stratégie par défaut de gestion des erreurs pour toutes les instances de la classe d' `SafeInt` dans votre code.  
  
> [!NOTE]
>  Une classe personnalisée qui gère les erreurs de la bibliothèque de SafeInt ne doit pas retourner le contrôle au code qui a appelé le gestionnaire d'erreurs.  Une fois le gestionnaire d'erreurs appelé, le résultat de l'opération d' `SafeInt` ne peut pas être approuvé.  
  
## Configuration requise  
 **En\-tête :** safeint.h  
  
 **Espace de noms :** msl::utilities  
  
## Voir aussi  
 [Miscellaneous Support Libraries Classes](http://msdn.microsoft.com/fr-fr/406fd46e-d53f-4096-ab40-36aa754c7a5c)   
 [Bibliothèque SafeInt](../windows/safeint-library.md)   
 [SafeIntException, classe](../windows/safeintexception-class.md)
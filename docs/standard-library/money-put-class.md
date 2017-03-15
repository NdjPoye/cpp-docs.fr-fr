---
title: "money_put, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::money_put"
  - "xlocmon/std::money_put"
  - "money_put"
  - "std.money_put"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "money_put (classe)"
ms.assetid: f439fd56-c9b1-414c-95e1-66c918c6eee6
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# money_put, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe de modèle décrit un objet pouvant servir de facette de paramètres régionaux pour contrôler les conversions de valeurs monétaires en séquences de type `CharType`.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <class CharType,  
    class OutputIterator = ostreambuf_iterator<CharType>>  
class money_put : public locale::facet;  
```  
  
#### <a name="parameters"></a>Paramètres  
 `CharType`  
 Type utilisé dans un programme pour encoder des caractères dans des paramètres régionaux spécifiques.  
  
 `OutputIterator`  
 Type d'itérateur dans lequel les fonctions put monétaires enregistrent leur sortie.  
  
## <a name="remarks"></a>Notes  
 Comme avec n'importe quelle facette de paramètres régionaux, l'ID d'objet statique possède une valeur stockée initiale de zéro. La première tentative d’accéder à sa valeur stockée stocke une valeur positive unique dans **id.**  
  
### <a name="constructors"></a>Constructeurs  
  
|||  
|-|-|  
|[money_put](#money_put__money_put)|Constructeur des objets de type `money_put`.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[char_type](#money_put__char_type)|Type utilisé pour décrire un caractère utilisé par des paramètres régionaux.|  
|[iter_type](#money_put__iter_type)|Type qui décrit un itérateur de sortie.|  
|[STRING_TYPE](#money_put__string_type)|Type qui décrit une chaîne contenant des caractères de type `CharType`.|  
  
### <a name="member-functions"></a>Fonctions membres  
  
|||  
|-|-|  
|[do_put](#money_put__do_put)|Fonction virtuelle appelée pour convertir un nombre ou une chaîne en une séquence de caractères représentant une valeur monétaire.|  
|[Put](#money_put__put)|Convertit un nombre ou une chaîne en une séquence de caractères représentant une valeur monétaire.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \< paramètres régionaux>  
  
 **Espace de noms :** std  
  
##  <a name="a-namemoneyputchartypea-moneyputchartype"></a><a name="money_put__char_type"></a>  money_put::char_type  
 Type utilisé pour décrire un caractère utilisé par des paramètres régionaux.  
  
```  
typedef CharType char_type;  
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme du paramètre de modèle **CharType**.  
  
##  <a name="a-namemoneyputdoputa-moneyputdoput"></a><a name="money_put__do_put"></a>  money_put::do_put  
 Fonction virtuelle appelée pour convertir un nombre ou une chaîne en une séquence de caractères représentant une valeur monétaire.  
  
```  
virtual iter_type do_put(
    iter_type next,   
    bool _Intl,   
    ios_base& _Iosbase,  
    CharType _Fill,   
    const string_type& val) const;

 
virtual iter_type do_put(
    iter_type next,   
    bool _Intl,   
    ios_base& _Iosbase,  
    CharType _Fill,  
    long double val) const;
```  
  
### <a name="parameters"></a>Paramètres  
 ` next`  
 Itérateur qui traite le premier élément de la chaîne insérée.  
  
 `_Intl`  
 Valeur booléenne indiquant le type de symbole monétaire attendu dans la séquence : **true** Si internationales, **false** Si nationales.  
  
 `_Iosbase`  
 Un format indicateur qui lorsque set indique que le symbole monétaire est facultatif. Sinon, il est requis  
  
 `_Fill`  
 Un caractère qui est utilisé pour l’espacement.  
  
 ` val`  
 Un objet de chaîne à convertir.  
  
### <a name="return-value"></a>Valeur de retour  
 Itérateur de sortie produits de la position située au-delà du dernier élément les adresses.  
  
### <a name="remarks"></a>Notes  
 La première fonction membre virtuelle génère des éléments séquentiels commençant à ` next` pour produire un champ de sortie monétaire à partir de la [string_type](#money_put__string_type) objet ` val`. La séquence contrôlée par ` val` doit commencer par un ou plusieurs chiffres décimaux, éventuellement précédés d’un signe moins (-), qui représente la quantité. La fonction retourne un itérateur désignant le premier élément après le champ de sortie monétaire générée.  
  
 La deuxième fonction membre virtuelle comporte comme la première, sauf qu’elle convertit efficacement première ` val` à une séquence de chiffres décimaux, éventuellement précédé d’un signe moins, puis convertit cette séquence comme indiqué ci-dessus.  
  
 Le format d’un champ de sortie monétaire est déterminé par le [facette de paramètres régionaux](../standard-library/locale-class.md#facet_class) fac retourné par l’appel (réelle) [use_facet](../Topic/%3Clocale%3E%20functions.md#use_facet) < [moneypunct](../standard-library/moneypunct-class.md)\< **CharType**, **intl**>> ( **iosbase**. [getloc](../standard-library/ios-base-class.md#ios_base__getloc)).  
  
 Plus précisément :  
  
- **fac**. [pos_format](../standard-library/moneypunct-class.md#moneypunct__pos_format) détermine l’ordre dans lequel les composants du champ sont générés pour une valeur non négative.  
  
- **fac**. [neg_format](../standard-library/moneypunct-class.md#moneypunct__neg_format) détermine l’ordre dans lequel les composants du champ sont générés pour une valeur négative.  
  
- **fac**. [curr_symbol](../standard-library/moneypunct-class.md#moneypunct__curr_symbol) détermine la séquence d’éléments pour générer un symbole de devise.  
  
- **fac**. [positive_sign](../standard-library/moneypunct-class.md#moneypunct__positive_sign) détermine la séquence d’éléments pour générer un signe positif.  
  
- **fac**. [negative_sign](../standard-library/moneypunct-class.md#moneypunct__negative_sign) détermine la séquence d’éléments pour générer un signe négatif.  
  
- **fac**. [regroupement](../standard-library/moneypunct-class.md#moneypunct__grouping) détermine la manière dont les chiffres sont regroupés à gauche de la virgule décimale.  
  
- **fac**. [thousands_sep](../standard-library/moneypunct-class.md#moneypunct__thousands_sep) détermine l’élément qui sépare les groupes de chiffres à gauche de la virgule décimale.  
  
- **fac**. [decimal_point](../standard-library/moneypunct-class.md#moneypunct__decimal_point) détermine l’élément qui sépare les chiffres entiers de tous les chiffres de fraction.  
  
- **fac**. [frac_digits](../standard-library/moneypunct-class.md#moneypunct__frac_digits) détermine le nombre de chiffres significatifs à droite de la virgule décimale.  
  
 Si la chaîne de connexion ( **fac**. `negative_sign` ou **fac**. `positive_sign`) comporte plusieurs éléments, seul le premier élément est généré lorsque l’élément égal à **money_base::sign** apparaît dans le modèle de format ( **fac**. `neg_format` ou **fac**. `pos_format`). Les éléments restants sont générés à la fin du champ de sortie monétaire.  
  
 Si **iosbase**. [indicateurs](../standard-library/ios-base-class.md#ios_base__flags) & [showbase](../Topic/%3Cios%3E%20functions.md#showbase) est différent de zéro, la chaîne **fac**. `curr_symbol` est généré lorsque l’élément égal à **money_base::symbol** apparaît dans le modèle de format. Sinon, aucun symbole monétaire n’est générée.  
  
 Si aucun regroupement des contraintes n’imposées par **fac**. **regroupement** (le premier élément a la valeur CHAR_MAX), puis aucune instance de **fac**. `thousands_sep` sont générés dans la partie de la valeur du champ de sortie monétaire (où l’élément égal à **money_base::value** apparaît dans le modèle de format). Si **fac**. `frac_digits` est zéro, alors aucune instance de **fac**. `decimal_point` est généré après les chiffres décimaux. Dans le cas contraire, le champ de sortie monétaire résultant place le poids faible **fac**. `frac_digits` chiffres décimaux à droite de la virgule décimale.  
  
 Marge intérieure se produit que pour n’importe quel champ de sortie numérique, sauf que si **iosbase**. **indicateurs** & **iosbase**. [interne](../Topic/%3Cios%3E%20functions.md#internal) est différente de zéro, tout état interne de remplissage est générée lorsque l’élément égal à **money_base::space** apparaît dans le modèle de format, si elle s’affiche. Sinon, le remplissage interne se produit avant la séquence générée. Le caractère de remplissage est **remplissage**.  
  
 Les appels de fonction **iosbase**. **largeur**(0) pour réinitialiser la largeur du champ à zéro.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [put](#money_put__put), où la fonction membre virtuelle est appelée par **put**.  
  
##  <a name="a-namemoneyputitertypea-moneyputitertype"></a><a name="money_put__iter_type"></a>  money_put::iter_type  
 Type qui décrit un itérateur de sortie.  
  
```  
typedef OutputIterator iter_type;  
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme du paramètre de modèle **OutputIterator.**  
  
##  <a name="a-namemoneyputmoneyputa-moneyputmoneyput"></a><a name="money_put__money_put"></a>  money_put::money_put  
 Constructeur des objets de type `money_put`.  
  
```  
explicit money_put(size_t _Refs = 0);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Refs`  
 Valeur entière qui sert à spécifier le type de gestion de la mémoire pour l’objet.  
  
### <a name="remarks"></a>Notes  
 Les valeurs possibles pour le `_Refs` paramètre et leur signification sont :  
  
-   0 : la durée de vie de l’objet est gérée par les paramètres régionaux qui le contiennent.  
  
-   1 : la durée de vie de l’objet doit être gérée manuellement.  
  
-   \> 0 : ces valeurs ne sont pas définis.  
  
 Aucun exemple directe n’est possibles, car le destructeur est protégé.  
  
 Le constructeur initialise les objets de base avec **paramètres régionaux ::**[facette](../standard-library/locale-class.md#facet_class)( `_Refs`).  
  
##  <a name="a-namemoneyputputa-moneyputput"></a><a name="money_put__put"></a>  money_put::Put  
 Convertit un nombre ou une chaîne en une séquence de caractères représentant une valeur monétaire.  
  
```  
iter_type put(
    iter_type next,   
    bool _Intl,   
    ios_base& _Iosbase,  
    CharType _Fill,   
    const string_type& val) const;

 
iter_type put(
    iter_type next,   
    bool _Intl,   
    ios_base& _Iosbase,  
    CharType _Fill,  
    long double val) const;
```  
  
### <a name="parameters"></a>Paramètres  
 ` next`  
 Itérateur qui traite le premier élément de la chaîne insérée.  
  
 `_Intl`  
 Valeur booléenne indiquant le type de symbole monétaire attendu dans la séquence : **true** Si internationales, **false** Si nationales.  
  
 `_Iosbase`  
 Un format indicateur qui lorsque set indique que le symbole monétaire est facultatif. Sinon, il est requis  
  
 `_Fill`  
 Un caractère qui est utilisé pour l’espacement.  
  
 ` val`  
 Un objet de chaîne à convertir.  
  
### <a name="return-value"></a>Valeur de retour  
 Itérateur de sortie produits de la position située au-delà du dernier élément les adresses.  
  
### <a name="remarks"></a>Notes  
 Les deux fonctions membres retournent [do_put](#money_put__do_put)( ` next`, `_Intl`, `_Iosbase`, `_Fill`, ` val`).  
  
### <a name="example"></a>Exemple  
  
```  
// money_put_put.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
//   locale loc( "german_germany" );  
   locale loc( "english_canada" );  
   basic_stringstream<char> psz, psz2;  
   ios_base::iostate st = 0;  
  
   psz2.imbue( loc );  
   psz2.flags( psz2.flags( )|ios_base::showbase ); // force the printing of the currency symbol  
   use_facet < money_put < char > >(loc).put(basic_ostream<char>::_Iter( psz2.rdbuf( ) ), true, psz2, st, 100012);  
   if (st & ios_base::failbit)  
      cout << "money_put( ) FAILED" << endl;  
   else  
      cout << "money_put( ) = \"" << psz2.rdbuf( )->str( ) <<"\""<< endl;     
  
   st = 0;  
};  
```  
  
```Output  
money_put( ) = "CAD1,000.12"  
```  
  
##  <a name="a-namemoneyputstringtypea-moneyputstringtype"></a><a name="money_put__string_type"></a>  money_put::STRING_TYPE  
 Un type qui décrit une chaîne contenant des caractères de type **CharType**.  
  
```  
typedef basic_string<CharType, Traits, Allocator> string_type;  
```  
  
### <a name="remarks"></a>Notes  
 Type qui décrit une spécialisation de classe de modèle [basic_string](../standard-library/basic-string-class.md) dont les objets peuvent stocker des séquences d’éléments de la séquence source.  
  
## <a name="see-also"></a>Voir aussi  
 [\< paramètres régionaux>](../standard-library/locale.md)   
 [Facet, classe](../standard-library/locale-class.md#facet_class)   
 [Sécurité des threads dans la bibliothèque Standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)


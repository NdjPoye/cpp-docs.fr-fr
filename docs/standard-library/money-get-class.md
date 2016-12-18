---
title: "money_get, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "xlocmon/std::money_get"
  - "money_get"
  - "std.money_get"
  - "std::money_get"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "money_get (classe)"
ms.assetid: 692d3374-3fe7-4b46-8aeb-f8d91ed66b2e
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# money_get, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe de modèle décrit un objet pouvant servir de facette de paramètres régionaux pour contrôler les conversions de séquences de type `CharType` en valeurs monétaires.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class CharType, class InputIterator = istreambuf_iterator<CharType>>  
class money_get : public locale::facet;
```  
  
#### <a name="parameters"></a>Paramètres  
 `CharType`  
 Type utilisé dans un programme pour encoder des caractères dans des paramètres régionaux spécifiques.  
  
 `InputIterator`  
 Type d'itérateur depuis lequel les fonctions get lisent leur entrée.  
  
## <a name="remarks"></a>Notes  
 Comme avec n'importe quelle facette de paramètres régionaux, l'ID d'objet statique possède une valeur stockée initiale de zéro. La première tentative d’accéder à sa valeur stockée stocke une valeur positive unique dans **id.**  
  
### <a name="constructors"></a>Constructeurs  
  
|||  
|-|-|  
|[money_get](#money_get__money_get)|Constructeur des objets de type `money_get` utilisés pour extraire des valeurs numériques de séquences représentant des valeurs monétaires.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[char_type](#money_get__char_type)|Type utilisé pour décrire un caractère utilisé par des paramètres régionaux.|  
|[iter_type](#money_get__iter_type)|Type qui décrit un itérateur d'entrée.|  
|[STRING_TYPE](#money_get__string_type)|Type qui décrit une chaîne contenant des caractères de type `CharType`.|  
  
### <a name="member-functions"></a>Fonctions membres  
  
|||  
|-|-|  
|[do_get](#money_get__do_get)|Fonction virtuelle appelée pour extraire une valeur numérique d'une séquence de caractères représentant une valeur monétaire.|  
|[Télécharger](#money_get__get)|Extrait une valeur numérique d'une séquence de caractères représentant une valeur monétaire.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \< paramètres régionaux>  
  
 **Espace de noms :** std  
  
##  <a name="a-namemoneygetchartypea-moneygetchartype"></a><a name="money_get__char_type"></a>  money_get::char_type  
 Type utilisé pour décrire un caractère utilisé par des paramètres régionaux.  
  
```
typedef CharType char_type;
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme du paramètre de modèle **CharType**.  
  
##  <a name="a-namemoneygetdogeta-moneygetdoget"></a><a name="money_get__do_get"></a>  money_get::do_get  
 Fonction virtuelle appelée pour extraire une valeur numérique à partir d’une séquence de caractères qui représente une valeur monétaire.  
  
```
virtual iter_type do_get(iter_type first,
    iter_type last,
    bool _Intl,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long double& val) const virtual iter_type do_get(iter_type first,
    iter_type last,
    bool _Intl,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    string_type& val) const
```  
  
### <a name="parameters"></a>Paramètres  
 `first`  
 Itérateur d’entrée d’adressage du début de la séquence à convertir.  
  
 `last`  
 Itérateur d’entrée traite la fin de la séquence à convertir.  
  
 `_Intl`  
 Valeur booléenne indiquant le type de symbole monétaire attendu dans la séquence : **true** Si internationales, **false** Si nationales.  
  
 `_Iosbase`  
 Un format indicateur qui lorsque set indique que le symbole monétaire est facultatif. dans le cas contraire, il est nécessaire.  
  
 `_State`  
 Définit les éléments de masque de bits appropriés pour l’état de flux de données en fonction de si les opérations ont réussi ou non.  
  
 `val`  
 Une chaîne de stocker la séquence convertie.  
  
### <a name="return-value"></a>Valeur de retour  
 Itérateur d’entrée qui traite le premier élément au-delà du champ d’entrée monétaire.  
  
### <a name="remarks"></a>Notes  
 La première fonction membre virtuelle tente de faire correspondre des éléments séquentiels commençant au début de la séquence [ `first`, `last`) jusqu'à ce qu’il a reconnu complète, nonempty monétaire d’entrée de champ. Si réussie, il convertit ce champ en une séquence d’un ou plusieurs chiffres décimaux, éventuellement précédé d’un signe moins ( `–`), pour représenter la quantité et stocke le résultat dans le [string_type](#money_get__string_type) objet `val`. Elle retourne un itérateur désignant le premier élément après le champ d’entrée monétaire. Sinon, la fonction stocke une séquence vide dans `val` et définit `ios_base::failbit` dans `_State`. Elle retourne un itérateur désignant le premier élément après n’importe quel préfixe d’un champ d’entrée monétaire valid. Dans les deux cas, si la valeur de retour est égale à `last`, la fonction définit `ios_base::eofbit` dans `_State`.  
  
 La seconde fonction membre virtuelle comporte comme la première, sauf qu’en cas de réussite, il convertit la séquence de chiffres éventuellement signé à une valeur de type `long double` et stocke cette valeur dans `val`.  
  
 Le format d’un champ d’entrée monétaire est déterminé par le [facette de paramètres régionaux](../standard-library/locale-class.md#facet_class)**fac** retourné par l’appel effectif [use_facet](../Topic/%3Clocale%3E%20functions.md#use_facet) < [moneypunct](../standard-library/moneypunct-class.md)\< **CharType**, **intl**>> ( **iosbase**. [getloc](../standard-library/ios-base-class.md#ios_base__getloc)).  
  
 Plus précisément :  
  
- **fac**. [neg_format](../standard-library/moneypunct-class.md#moneypunct__neg_format) détermine l’ordre dans lequel les composants du champ se produisent.  
  
- **fac**. [curr_symbol](../standard-library/moneypunct-class.md#moneypunct__curr_symbol) détermine l’ordre des éléments qui constituent un symbole de devise.  
  
- **fac**. [positive_sign](../standard-library/moneypunct-class.md#moneypunct__positive_sign) détermine l’ordre des éléments qui constituent un signe positif.  
  
- **fac**. [negative_sign](../standard-library/moneypunct-class.md#moneypunct__negative_sign) détermine l’ordre des éléments qui constituent un signe négatif.  
  
- **fac**. [regroupement](../standard-library/moneypunct-class.md#moneypunct__grouping) détermine la manière dont les chiffres sont regroupés à gauche de la virgule décimale.  
  
- **fac**. [thousands_sep](../standard-library/moneypunct-class.md#moneypunct__thousands_sep) détermine l’élément qui sépare les groupes de chiffres à gauche de la virgule décimale.  
  
- **fac**. [decimal_point](../standard-library/moneypunct-class.md#moneypunct__decimal_point) détermine l’élément qui sépare les chiffres entiers les chiffres de fraction.  
  
- **fac**. [frac_digits](../standard-library/moneypunct-class.md#moneypunct__frac_digits) détermine le nombre de chiffres significatifs à droite de la virgule décimale. Lors de l’analyse d’un montant monétaire avec plus de chiffres de fraction que sont appelées pour par `frac_digits`, `do_get` arrête l’analyse après la consommation au plus `frac_digits` caractères.  
  
 Si la chaîne de connexion ( **fac**. `negative_sign` ou **fac**. `positive_sign`) comporte plusieurs éléments, seul le premier élément est mis en correspondance dans lequel l’élément égal à **money_base::sign** apparaît dans le modèle de format ( **fac**. `neg_format`). Les éléments restants sont mis en correspondance à la fin du champ d’entrée monétaire. Si aucune chaîne n’a un premier élément qui correspond à l’élément suivant dans le champ d’entrée monétaire, la chaîne de connexion est traitée comme vide et le signe est un nombre positif.  
  
 Si **iosbase**. [indicateurs](../standard-library/ios-base-class.md#ios_base__flags) & [showbase](../Topic/%3Cios%3E%20functions.md#showbase) est différent de zéro, la chaîne **fac**. `curr_symbol` doit correspondre au où l’élément égal à **money_base::symbol** apparaît dans le modèle de format. Sinon, si **money_base::symbol** se produit à la fin du modèle de format, et si aucun élément de la chaîne de connexion est conservé pour être mises en correspondance, le symbole de devise n’est pas mis en correspondance. Dans le cas contraire, le symbole de devise est éventuellement mis en correspondance.  
  
 Si aucune instance de **fac**. `thousands_sep` se produit dans la partie de la valeur du champ d’entrée monétaire (où l’élément égal à **money_base::value** apparaît dans le modèle de format), aucune contrainte de regroupement n’est imposée. Sinon, n’importe quel regroupement de contraintes imposées par **fac**. **regroupement** est appliquée. Notez que la séquence de chiffres qui en résulte représente un entier dont poids faible **fac**. `frac_digits` chiffres décimaux sont considérés comme à droite de la virgule décimale.  
  
 Un espace blanc arbitraire est mis en correspondance dans lequel l’élément égal à **money_base::space** apparaît dans le modèle de format, si autre que s’affiche à la fin du modèle de format. Dans le cas contraire, aucun espace blanc interne n’est mis en correspondance. Un élément *ch* est considéré comme un espace blanc si [use_facet](../Topic/%3Clocale%3E%20functions.md#use_facet) < [ctype](../standard-library/ctype-class.md)\< **CharType**>> ( **iosbase**. [getloc](../standard-library/ios-base-class.md#ios_base__getloc)). [est](../standard-library/ctype-class.md#ctype__is)( **ctype_base::space**, *ch*) est **true**.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [obtenir](#money_get__get), qui appelle la méthode `do_get`.  
  
##  <a name="a-namemoneygetgeta-moneygetget"></a><a name="money_get__get"></a>  money_get::Get  
 Extrait une valeur numérique d'une séquence de caractères représentant une valeur monétaire.  
  
```
iter_type get(iter_type first,
    iter_type last,
    bool _Intl,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long double& val) const;

iter_type get(iter_type first,
    iter_type last,
    bool _Intl,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    string_type& val) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `first`  
 Itérateur d’entrée d’adressage du début de la séquence à convertir.  
  
 `last`  
 Itérateur d’entrée traite la fin de la séquence à convertir.  
  
 `_Intl`  
 Valeur booléenne indiquant le type de symbole monétaire attendu dans la séquence : **true** Si internationales, **false** Si nationales.  
  
 `_Iosbase`  
 Un format indicateur qui lorsque set indique que le symbole monétaire est facultatif. Sinon, il est requis  
  
 `_State`  
 Définit les éléments de masque de bits appropriés pour l’état de flux de données en fonction de la réussite des opérations.  
  
 `val`  
 Une chaîne de stocker la séquence convertie.  
  
### <a name="return-value"></a>Valeur de retour  
 Itérateur d’entrée qui traite le premier élément au-delà du champ d’entrée monétaire.  
  
### <a name="remarks"></a>Notes  
 Les deux fonctions membres retournent [do_get](#money_get__do_get)( `first``,` `last``,` `_Intl`, `_Iosbase`, `_State`, `val`).  
  
### <a name="example"></a>Exemple  
  
```  
// money_get_get.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
  
int main( )  
{  
   locale loc( "german_germany" );  
  
   basic_stringstream< char > psz;  
   psz << use_facet<moneypunct<char, 1> >(loc).curr_symbol() << "-1.000,56";  
   basic_stringstream< char > psz2;  
   psz2 << "-100056" << use_facet<moneypunct<char, 1> >(loc).curr_symbol();  
  
   ios_base::iostate st = 0;  
   long double fVal;  
  
   psz.flags( psz.flags( )|ios_base::showbase );   
   // Which forced the READING the currency symbol  
   psz.imbue(loc);  
   use_facet < money_get < char > >( loc ).  
      get( basic_istream<char>::_Iter( psz.rdbuf( ) ),     
           basic_istream<char>::_Iter( 0 ), true, psz, st, fVal );  
  
   if ( st & ios_base::failbit )  
      cout << "money_get(" << psz.str( ) << ", intl = 1) FAILED"  
           << endl;  
   else  
      cout << "money_get(" << psz.str( ) << ", intl = 1) = "   
           << fVal/100.0 << endl;  
  
   use_facet < money_get < char > >( loc ).  
      get(basic_istream<char>::_Iter(psz2.rdbuf( )),     
          basic_istream<char>::_Iter(0), false, psz2, st, fVal);  
  
   if ( st & ios_base::failbit )  
      cout << "money_get(" << psz2.str( ) << ", intl = 0) FAILED"   
           << endl;  
   else  
      cout << "money_get(" << psz2.str( ) << ", intl = 0) = "   
           << fVal/100.0 << endl;  
};  
```  
  
##  <a name="a-namemoneygetitertypea-moneygetitertype"></a><a name="money_get__iter_type"></a>  money_get::iter_type  
 Type qui décrit un itérateur d'entrée.  
  
```
typedef InputIterator iter_type;
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme du paramètre de modèle **InputIterator**.  
  
##  <a name="a-namemoneygetmoneygeta-moneygetmoneyget"></a><a name="money_get__money_get"></a>  money_get::money_get  
 Constructeur des objets de type `money_get` utilisés pour extraire des valeurs numériques de séquences représentant des valeurs monétaires.  
  
```
explicit money_get(size_t _Refs = 0);
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
  
 Le constructeur initialise les objets de base avec **paramètres régionaux ::**[facette](../standard-library/locale-class.md#facet_class)( **_***Refs*).  
  
##  <a name="a-namemoneygetstringtypea-moneygetstringtype"></a><a name="money_get__string_type"></a>  money_get::STRING_TYPE  
 Un type qui décrit une chaîne contenant des caractères de type **CharType**.  
  
```
typedef basic_string<CharType, Traits, Allocator> string_type;
```  
  
### <a name="remarks"></a>Notes  
 Type qui décrit une spécialisation de classe de modèle [basic_string](../standard-library/basic-string-class.md).  
  
## <a name="see-also"></a>Voir aussi  
 [\< paramètres régionaux>](../standard-library/locale.md)   
 [Facet, classe](../standard-library/locale-class.md#facet_class)   
 [Sécurité des threads dans la bibliothèque Standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)




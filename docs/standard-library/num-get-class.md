---
title: "num_get, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "num_get"
  - "std::num_get"
  - "std.num_get"
  - "xlocnum/std::num_get"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "num_get (classe)"
ms.assetid: 9933735d-3918-4b17-abad-5fca2adc62d7
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# num_get, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Classe de modèle qui décrit un objet pouvant servir de facette de paramètres régionaux pour contrôler les conversions de séquences de type `CharType` en valeurs numériques.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class CharType, class InputIterator = istreambuf_iterator<CharType>>  
class num_get : public locale::facet;
```  
  
#### <a name="parameters"></a>Paramètres  
 `CharType`  
 Type utilisé dans un programme pour encoder des caractères dans des paramètres régionaux spécifiques.  
  
 `InputIterator`  
 Type d'itérateur depuis lequel les fonctions get numériques lisent leur entrée.  
  
## <a name="remarks"></a>Notes  
 Comme avec n'importe quelle facette de paramètres régionaux, l'ID d'objet statique possède une valeur stockée initiale de zéro. La première tentative d’accéder à sa valeur stockée stocke une valeur positive unique dans **id.**  
  
### <a name="constructors"></a>Constructeurs  
  
|||  
|-|-|  
|[num_get](#num_get__num_get)|Constructeur des objets de type `num_get` utilisés pour extraire des valeurs numériques depuis des séquences.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[char_type](#num_get__char_type)|Type utilisé pour décrire un caractère utilisé par des paramètres régionaux.|  
|[iter_type](#num_get__iter_type)|Type qui décrit un itérateur d'entrée.|  
  
### <a name="member-functions"></a>Fonctions membres  
  
|||  
|-|-|  
|[do_get](#num_get__do_get)|Fonction virtuelle appelée pour extraire une valeur numérique ou booléenne depuis une séquence de caractères.|  
|[Télécharger](#num_get__get)|Extrait une valeur numérique ou booléenne d'une séquence de caractères.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \< paramètres régionaux>  
  
 **Espace de noms :** std  
  
##  <a name="a-namenumgetchartypea-numgetchartype"></a><a name="num_get__char_type"></a>  num_get::char_type  
 Type utilisé pour décrire un caractère utilisé par des paramètres régionaux.  
  
```
typedef CharType char_type;
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme du paramètre de modèle **CharType**.  
  
##  <a name="a-namenumgetdogeta-numgetdoget"></a><a name="num_get__do_get"></a>  num_get::do_get  
 Fonction virtuelle appelée pour extraire une valeur numérique ou booléenne depuis une séquence de caractères.  
  
```
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long& val) const;virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned short& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned int& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned long& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long long& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned long long& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    float& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    double& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long double& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    void *& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    bool& val) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `first`  
 Début de la plage de caractères à partir duquel lire le nombre.  
  
 `last`  
 La fin de la plage de caractères à partir duquel lire le nombre.  
  
 `_Iosbase`  
 Le [ios_base](../standard-library/ios-base-class.md) dont les indicateurs sont utilisés par la conversion.  
  
 `_State`  
 L’état pour le failbit (voir [ios_base::iostate](../standard-library/ios-base-class.md#ios_base__iostate)) est ajouté en cas d’échec.  
  
 `val`  
 Valeur qui a été lue.  
  
### <a name="return-value"></a>Valeur de retour  
 L’itérateur une fois que la valeur a été lue.  
  
### <a name="remarks"></a>Notes  
 La première fonction membre virtuelle,  
  
 `virtual iter_type do_get(`  
  
 `iter_type first,`  
  
 `iter_type last,`  
  
 `ios_base& _Iosbase,`  
  
 `ios_base::iostate& _State,`  
  
 `long& val`  
  
 `) const;`  
  
 correspond à des éléments séquentiels commençant à `first` dans la séquence `[``first``,` `last``)` jusqu'à ce qu’il a reconnu complète, non vide entier d’entrée de champ. Si réussie, il convertit ce champ à sa valeur en tant que type équivalent `long``,` et stocke le résultat dans `val`. Elle retourne un itérateur désignant le premier élément après le champ d’entrée numérique. Sinon, la fonction enregistre rien dans `val` et définit `ios_base::failbit` dans `state`. Elle retourne un itérateur désignant le premier élément après n’importe quel préfixe d’un champ d’entrée d’entier valide. Dans les deux cas, si la valeur de retour est égale à `last`, la fonction définit `ios_base::eofbit` dans `state`.  
  
 Le champ d’entrée entière est converti selon les mêmes règles utilisées par les fonctions d’analyse de correspondance et de conversion d’une série de `char` les éléments d’un fichier. (Chacun de ces `char` élément est supposé être mappé à un élément de type équivalent `Elem` par un simple, un à un, mappage.) La spécification de conversion analyse équivalent est déterminée comme suit :  
  
 Si `iosbase.`[ios_base::flags](../standard-library/ios-base-class.md#ios_base__flags)`() & ios_base::basefield == ios_base::`[oct](../Topic/%3Cios%3E%20functions.md#oct), la spécification de conversion est `lo`.  
  
 Si `iosbase.flags() & ios_base::basefield == ios_base::`[hexadécimal](../Topic/%3Cios%3E%20functions.md#hex), la spécification de conversion est `lx`.  
  
 Si `iosbase.flags() & ios_base::basefield == 0`, la spécification de conversion est `li`.  
  
 Dans le cas contraire, la spécification de conversion est `ld`.  
  
 Le format d’un champ d’entrée entière est également déterminé par le [facette de paramètres régionaux](../standard-library/locale-class.md#facet_class)`fac` retourné par l’appel [use_facet](../Topic/%3Clocale%3E%20functions.md#use_facet) `<`[numpunct](../standard-library/numpunct-class.md)`<Elem>(iosbase.` [ios_base::getloc](../standard-library/ios-base-class.md#ios_base__getloc)`())`. Plus précisément :  
  
 `fac.` [numpunct::grouping](../standard-library/numpunct-class.md#numpunct__grouping) `()` Détermine la manière dont les chiffres sont regroupés à gauche de la virgule décimale  
  
 `fac.` [numpunct::thousands_sep](../standard-library/numpunct-class.md#numpunct__thousands_sep) `()` Détermine la séquence qui sépare les groupes de chiffres à gauche de la virgule décimale.  
  
 Si aucune instance de `fac.thousands_sep()` se produisent dans le champ d’entrée numérique, aucune contrainte de regroupement n’est imposée. Sinon, n’importe quel regroupement de contraintes imposées par `fac.grouping()` sont appliquées et les séparateurs sont supprimés avant que la conversion d’analyse se produit.  
  
 La fonction membre virtuelle quatrième :  
  
 `virtual iter_type do_get(`  
  
 `iter_type first,`  
  
 `iter_type last,`  
  
 `ios_base& _Iosbase,`  
  
 `ios_base::iostate& _State,`  
  
 `unsigned long& val`  
  
 `) const;`  
  
 se comporte comme la première, à ceci près qu’il remplace une spécification de conversion de `ld` avec `lu`. Si réussie il convertit le champ d’entrée numérique en une valeur de type `unsigned long` et stocke cette valeur dans `val`.  
  
 La fonction membre virtuelle cinquième :  
  
 `virtual iter_type do_get(`  
  
 `iter_type first,`  
  
 `iter_type last,`  
  
 `ios_base& _Iosbase,`  
  
 `ios_base::iostate& _State,`  
  
 `long long& val`  
  
 `) const;`  
  
 se comporte comme la première, à ceci près qu’il remplace une spécification de conversion de `ld` avec `lld`. Si réussie il convertit le champ d’entrée numérique en une valeur de type `long long` et stocke cette valeur dans `val`.  
  
 La fonction membre virtuelle sixième :  
  
 `virtual iter_type do_get(`  
  
 `iter_type first,`  
  
 `iter_type last,`  
  
 `ios_base& _Iosbase,`  
  
 `ios_base::iostate& _State,`  
  
 `unsigned long long& val`  
  
 `) const;`  
  
 se comporte comme la première, à ceci près qu’il remplace une spécification de conversion de `ld` avec `llu`. Si réussie il convertit le champ d’entrée numérique en une valeur de type `unsigned long long` et stocke cette valeur dans `val`.  
  
 La fonction membre virtuelle septième :  
  
 `virtual iter_type do_get(`  
  
 `iter_type first,`  
  
 `iter_type last,`  
  
 `ios_base& _Iosbase,`  
  
 `ios_base::iostate& _State,`  
  
 `float& val`  
  
 `) const;`  
  
 se comporte comme la première, sauf qu’il provoque un correspond à un champ d’entrée à virgule flottante complète et non vide. `fac.`[numpunct::decimal_point](../standard-library/numpunct-class.md#numpunct__decimal_point)`()` détermine la séquence qui sépare les chiffres entiers les chiffres de fraction. Le spécificateur de conversion analyse équivalent est `lf`.  
  
 La fonction membre virtuelle huitième :  
  
 `virtual iter_type do_get(`  
  
 `iter_type first,`  
  
 `iter_type last,`  
  
 `ios_base& _Iosbase,`  
  
 `ios_base::iostate& _State,`  
  
 `double& val`  
  
 `) const;`  
  
 se comporte comme la première, sauf qu’il provoque un correspond à un champ d’entrée à virgule flottante complète et non vide. `fac.`[numpunct::decimal_point](../standard-library/numpunct-class.md#numpunct__decimal_point)`()` détermine la séquence qui sépare les chiffres entiers les chiffres de fraction. Le spécificateur de conversion analyse équivalent est `lf`.  
  
 La fonction membre virtuelle neuvième :  
  
 `virtual iter_type do_get(`  
  
 `iter_type first,`  
  
 `iter_type last,`  
  
 `ios_base& _Iosbase,`  
  
 `ios_base::iostate& _State,`  
  
 `long double& val`  
  
 `) const;`  
  
 se comporte comme le huitième, sauf que le spécificateur de conversion analyse équivalent est `Lf`.  
  
 La fonction membre virtuelle neuvième :  
  
 `virtual iter_type do_get(`  
  
 `iter_type first,`  
  
 `iter_type last,`  
  
 `ios_base& _Iosbase,`  
  
 `ios_base::iostate& _State,`  
  
 `void *& val`  
  
 `) const;`  
  
 se comporte comme la première, sauf que le spécificateur de conversion analyse équivalent est `p`.  
  
 La dernière fonction membre virtuelle (onzième) :  
  
 `virtual iter_type do_get(`  
  
 `iter_type first,`  
  
 `iter_type last,`  
  
 `ios_base& _Iosbase,`  
  
 `ios_base::iostate& _State,`  
  
 `bool& val`  
  
 `) const;`  
  
 se comporte comme la première, mais il s’efforce de faire correspondre un champ d’entrée booléen complète et non vide. Si réussie il convertit le champ d’entrée booléens en une valeur de type `bool` et stocke cette valeur dans `val`.  
  
 Un champ d’entrée booléen prend l’une des deux formes. Si `iosbase.flags() & ios_base::`[boolalpha](../Topic/%3Cios%3E%20functions.md#boolalpha) est false, il est identique à un champ d’entrée entière, sauf que la valeur convertie doit être 0 (false) ou 1 (true). Dans le cas contraire, la séquence doit correspondre soit `fac.`[numpunct::falsename](../standard-library/numpunct-class.md#numpunct__falsename)`()` (pour false), ou `fac.`[numpunct::truename](../standard-library/numpunct-class.md#numpunct__truename)`()` (pour true).  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [obtenir](#num_get__get), où la fonction membre virtuelle est appelée par `do_get`.  
  
##  <a name="a-namenumgetgeta-numgetget"></a><a name="num_get__get"></a>  num_get::Get  
 Extrait une valeur numérique ou booléenne d'une séquence de caractères.  
  
```
iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    bool& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned short& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned int& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned long& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long long& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned long long& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    float& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    double& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long double& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    void *& val) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `first`  
 Début de la plage de caractères à partir duquel lire le nombre.  
  
 `last`  
 La fin de la plage de caractères à partir duquel lire le nombre.  
  
 `_Iosbase`  
 Le [ios_base](../standard-library/ios-base-class.md) dont les indicateurs sont utilisés par la conversion.  
  
 `_State`  
 L’état pour le failbit (voir [ios_base::iostate](../standard-library/ios-base-class.md#ios_base__iostate)) est ajouté en cas d’échec.  
  
 `val`  
 Valeur qui a été lue.  
  
### <a name="return-value"></a>Valeur de retour  
 L’itérateur une fois que la valeur a été lue.  
  
### <a name="remarks"></a>Notes  
 Retournent toutes les fonctions membres [do_get](#num_get__do_get)( `first`, `last`, `_Iosbase`, `_State`, `val`).  
  
 La première fonction membre virtuelle tente de faire correspondre des éléments séquentiels commençant au début de la séquence [ `first`, `last`) jusqu'à ce qu’il a reconnu complète, non vide entier d’entrée de champ. Si réussie, il convertit ce champ à sa valeur en tant que type équivalent **long** et stocke le résultat dans `val`. Elle retourne un itérateur désignant le premier élément après le champ d’entrée numérique. Sinon, la fonction enregistre rien dans `val` et définit `ios_base::failbit` dans _ *état*. Elle retourne un itérateur désignant le premier élément après n’importe quel préfixe d’un champ d’entrée d’entier valide. Dans les deux cas, si la valeur de retour est égale à **dernière**, la fonction définit `ios_base::eofbit` dans `_State`.  
  
 Le champ d’entrée entière est converti selon les mêmes règles utilisées par les fonctions d’analyse de correspondance et de conversion d’une série de `char` les éléments d’un fichier. Chacun de ces `char` élément est supposé être mappé à un élément de type équivalent **CharType** par un mappage simple, un à un. La spécification de conversion analyse équivalent est déterminée comme suit :  
  
-   Si **iosbase**. [indicateurs](../standard-library/ios-base-class.md#ios_base__flags) & `ios_base::basefield` == `ios_base::`[oct](../Topic/%3Cios%3E%20functions.md#oct), la spécification de conversion est **lo**.  
  
-   Si **iosbase.flags** & **ios_base::basefield** == `ios_base::`[hexadécimal](../Topic/%3Cios%3E%20functions.md#hex), la spécification de conversion est **lx**.  
  
-   Si **iosbase.flags** & **ios_base::basefield** == 0, la spécification de conversion est `li`.  
  
-   Dans le cas contraire, la spécification de conversion est **%ld**.  
  
 Le format d’un champ d’entrée entière est également déterminé par le [facette de paramètres régionaux](../standard-library/locale-class.md#facet_class)**fac** retourné par l’appel [use_facet](../Topic/%3Clocale%3E%20functions.md#use_facet) < [numpunct](../standard-library/numpunct-class.md)\< **Elem**> ( **iosbase**. [getloc](../standard-library/ios-base-class.md#ios_base__getloc)). Plus précisément :  
  
- **fac**. [regroupement](../standard-library/numpunct-class.md#numpunct__grouping) détermine la manière dont les chiffres sont regroupés à gauche de la virgule décimale.  
  
- **fac**. [thousands_sep](../standard-library/numpunct-class.md#numpunct__thousands_sep) détermine la séquence qui sépare les groupes de chiffres à gauche de la virgule décimale.  
  
 Si aucune instance de **fac**. `thousands_sep` se produit dans le champ d’entrée numérique, aucune contrainte de regroupement n’est imposée. Sinon, n’importe quel regroupement de contraintes imposées par **fac**. **regroupement** est appliquée et les séparateurs sont supprimés avant que la conversion d’analyse se produit.  
  
 La deuxième fonction membre virtuelle :  
  
```
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned long& val) const;
```  
  
 se comporte comme la première, à ceci près qu’il remplace une spécification de conversion de **%ld** avec **lu**. Si réussie, il convertit le champ d’entrée numérique en une valeur de type `unsigned long` et stocke cette valeur dans `val`.  
  
 La troisième fonction membre virtuelle :  
  
```
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    double& val) const;
```  
  
 se comporte comme la première, sauf qu’il tente de correspondre à un champ d’entrée à virgule flottante complète et non vide. **fac**. [decimal_point](../standard-library/numpunct-class.md#numpunct__decimal_point) détermine la séquence qui sépare les chiffres entiers les chiffres de fraction. Le spécificateur de conversion analyse équivalent est **lf**.  
  
 La fonction membre virtuelle quatrième :  
  
```
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long double& val) const;
```  
  
 se comporte comme le troisième, sauf que le spécificateur de conversion analyse équivalent est **Lf**.  
  
 La fonction membre virtuelle cinquième :  
  
```
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    void *& val) const;
```  
  
 se comporte comme la première, sauf que le spécificateur de conversion analyse équivalent est **p**.  
  
 La fonction membre virtuelle sixième :  
  
```
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    bool& val) const;
```  
  
 se comporte comme la première, sauf qu’il tente de correspondre à un champ d’entrée booléen complète et non vide. Si réussie il convertit le champ d’entrée booléens en une valeur de type `bool` et stocke cette valeur dans `val`.  
  
 Un champ d’entrée booléen prend l’une des deux formes. Si **iosbase**. **indicateurs** & `ios_base::`[boolalpha](../Topic/%3Cios%3E%20functions.md#boolalpha) est **false**, il est identique à un champ d’entrée entière, sauf que la valeur convertie doit être 0 (pour **false**) ou 1 (pour **true**). Dans le cas contraire, la séquence doit correspondre soit **fac**. [falsename](../standard-library/numpunct-class.md#numpunct__falsename) (pour **false**), ou **fac**. [TrueName](../standard-library/numpunct-class.md#numpunct__truename) (pour **true**).  
  
### <a name="example"></a>Exemple  
  
```  
// num_get_get.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "german_germany" );  
  
   basic_stringstream<char> psz, psz2;  
   psz << "-1000,56";  
  
   ios_base::iostate st = 0;  
   long double fVal;  
   cout << use_facet <numpunct <char> >(loc).thousands_sep( ) << endl;  
  
   psz.imbue( loc );  
   use_facet <num_get <char> >  
   (loc).get( basic_istream<char>::_Iter( psz.rdbuf( ) ),  
           basic_istream<char>::_Iter(0), psz, st, fVal );  
  
   if ( st & ios_base::failbit )  
      cout << "money_get( ) FAILED" << endl;  
   else  
      cout << "money_get( ) = " << fVal << endl;  
}  
```  
  
##  <a name="a-namenumgetitertypea-numgetitertype"></a><a name="num_get__iter_type"></a>  num_get::iter_type  
 Type qui décrit un itérateur d'entrée.  
  
```
typedef InputIterator iter_type;
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme du paramètre de modèle **InputIterator**.  
  
##  <a name="a-namenumgetnumgeta-numgetnumget"></a><a name="num_get__num_get"></a>  num_get::num_get  
 Constructeur des objets de type `num_get` utilisés pour extraire des valeurs numériques depuis des séquences.  
  
```
explicit num_get(size_t _Refs = 0);
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
  
## <a name="see-also"></a>Voir aussi  
 [\< paramètres régionaux>](../standard-library/locale.md)   
 [Facet, classe](../standard-library/locale-class.md#facet_class)   
 [Sécurité des threads dans la bibliothèque Standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)




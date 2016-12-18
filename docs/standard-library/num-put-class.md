---
title: "num_put, classe | Microsoft Docs"
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
  - "std::num_put"
  - "xlocnum/std::num_put"
  - "num_put"
  - "std.num_put"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "num_put (classe)"
ms.assetid: 36c5bffc-8283-4201-8ed4-78c4d81f8a17
caps.latest.revision: 21
caps.handback.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# num_put, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Classe de modèle qui décrit un objet pouvant servir de facette de paramètres régionaux pour contrôler les conversions de valeurs numériques en séquences de type `CharType`.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <class CharType,  
    class OutputIterator = ostreambuf_iterator<CharType>>  
class num_put : public locale::facet;  
```  
  
#### <a name="parameters"></a>Paramètres  
 `CharType`  
 Type utilisé dans un programme pour encoder des caractères dans des paramètres régionaux spécifiques.  
  
 `OutputIterator`  
 Type d'itérateur dans lequel les fonctions numériques Put écrivent leur sortie.  
  
## <a name="remarks"></a>Notes  
 Comme avec n'importe quelle facette de paramètres régionaux, l'ID d'objet statique possède une valeur stockée initiale de zéro. La première tentative d’accéder à sa valeur stockée stocke une valeur positive unique dans **id.**  
  
### <a name="constructors"></a>Constructeurs  
  
|||  
|-|-|  
|[num_put](#num_put__num_put)|Constructeur des objets de type `num_put`.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[char_type](#num_put__char_type)|Type utilisé pour décrire un caractère utilisé par des paramètres régionaux.|  
|[iter_type](#num_put__iter_type)|Type qui décrit un itérateur de sortie.|  
  
### <a name="member-functions"></a>Fonctions membres  
  
|||  
|-|-|  
|[do_put](#num_put__do_put)|Fonction virtuelle qui est appelée pour convertir un nombre en une séquence de `CharType` qui représente le nombre au format de paramètres régionaux donnés.|  
|[Put](#num_put__put)|Convertit un nombre en une séquence de `CharType` qui représente le nombre au format de paramètres régionaux donnés.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \< paramètres régionaux>  
  
 **Espace de noms :** std  
  
##  <a name="a-namenumputchartypea-numputchartype"></a><a name="num_put__char_type"></a>  num_put::char_type  
 Type utilisé pour décrire un caractère utilisé par des paramètres régionaux.  
  
```  
typedef CharType char_type;  
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme du paramètre de modèle **CharType**.  
  
##  <a name="a-namenumputdoputa-numputdoput"></a><a name="num_put__do_put"></a>  num_put::do_put  
 Une fonction virtuelle appelée pour convertir un nombre en une séquence de **CharType**qui représente le nombre au format de paramètres régionaux donnés.  
  
```  
virtual iter_type do_put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    bool val) const;

 
virtual iter_type do_put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    long val) const;

 
virtual iter_type do_put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    unsigned long val) const;

 
virtual iter_type do_put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    double val) const;

 
virtual iter_type do_put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    long double val) const;

 
virtual iter_type do_put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    const void* val) const;

 
virtual iter_type do_put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    const long long val) const;

virtual iter_type do_put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    const unsigned long long val) const;
```  
  
### <a name="parameters"></a>Paramètres  
 ` next`  
 Itérateur qui traite le premier élément de la chaîne insérée.  
  
 `_Iosbase`  
 Spécifié le flux qui contient des paramètres régionaux avec la facette numpunct utilisée pour les signes de ponctuation entre les indicateurs de mise en forme la sortie et de sortie.  
  
 `_Fill`  
 Un caractère qui est utilisé pour l’espacement.  
  
 ` val`  
 Le nombre ou type booléen qui est en sortie.  
  
### <a name="return-value"></a>Valeur de retour  
 Itérateur de sortie produits de la position située au-delà du dernier élément les adresses.  
  
### <a name="remarks"></a>Notes  
 La première fonction membre virtuelle génère des éléments séquentiels commençant à ` next` pour produire un champ de sortie entier de la valeur de ` val`. La fonction retourne un itérateur désignant l’emplacement suivant pour insérer un élément après le champ de résultat entier généré.  
  
 Le champ de résultat entier est généré par les mêmes règles utilisées par les fonctions d’impression pour la génération d’une série de `char` les éléments dans un fichier. Chaque élément de ce type char est supposé être mappé à un élément de type équivalent **CharType** par un mappage simple, un à un. Lorsqu’une fonction d’impression remplit un champ avec des espaces ou le chiffre 0, toutefois, `do_put` utilise à la place **remplissage**. La spécification de conversion d’impression équivalent est déterminée comme suit :  
  
-   Si **iosbase**. [indicateurs](../standard-library/ios-base-class.md#ios_base__flags) & `ios_base::basefield` == `ios_base::`[oct](../Topic/%3Cios%3E%20functions.md#oct), la spécification de conversion est **lo**.  
  
-   Si **iosbase.flags** & **ios_base::basefield** == `ios_base::`[hexadécimal](../Topic/%3Cios%3E%20functions.md#hex), la spécification de conversion est **lx**.  
  
-   Dans le cas contraire, la spécification de conversion est **%ld**.  
  
 Si **iosbase**. [largeur](../standard-library/ios-base-class.md#ios_base__width) est différent de zéro, une largeur de champ de cette valeur est ajoutée. La fonction appelle ensuite **iosbase**. **largeur**(0) pour réinitialiser la largeur du champ à zéro.  
  
 Marge intérieure se produit uniquement si le nombre minimal d’éléments *N* doit spécifier le champ de sortie est inférieure à **iosbase**. [largeur](../standard-library/ios-base-class.md#ios_base__width). Ce type de remplissage se compose d’une séquence de *N* – **largeur** copie de **remplissage**. Remplissage puis se déroule comme suit :  
  
-   Si **iosbase**. **indicateurs** & `ios_base::adjustfield` == `ios_base::`[gauche](../Topic/%3Cios%3E%20functions.md#left), l’indicateur **–** est ajouté. (Marge intérieure se produit après le texte généré.)  
  
-   Si **iosbase.flags** & **ios_base::adjustfield** == `ios_base::`[interne](../Topic/%3Cios%3E%20functions.md#internal), l’indicateur **0** est ajouté. (Pour un champ de sortie numérique, remplissage se produit lorsque les fonctions d’impression de remplissage 0.)  
  
-   Dans le cas contraire, aucun indicateur supplémentaire n’est ajouté. (Marge intérieure se produit avant la séquence générée.)  
  
 Enfin :  
  
-   Si **iosbase**. **indicateurs** & `ios_base::`[showpos](../Topic/%3Cios%3E%20functions.md#showpos) est différent de zéro, l’indicateur **+** est ajouté à la spécification de conversion.  
  
-   Si **iosbase**. **indicateurs** & **ios_base ::**[showbase](../Topic/%3Cios%3E%20functions.md#showbase) est différent de zéro, l’indicateur **#** est ajouté à la spécification de conversion.  
  
 Le format d’un nombre entier de sortie champ est également déterminé par le [facette de paramètres régionaux](../standard-library/locale-class.md#facet_class)**fac** retourné par l’appel [use_facet](../Topic/%3Clocale%3E%20functions.md#use_facet) < [numpunct](../standard-library/numpunct-class.md)\< **Elem**> ( **iosbase**. [getloc](../standard-library/ios-base-class.md#ios_base__getloc)). Plus précisément :  
  
- **fac**. [regroupement](../standard-library/numpunct-class.md#numpunct__grouping) détermine la manière dont les chiffres sont regroupés à gauche de la virgule décimale  
  
- **fac**. [thousands_sep](../standard-library/numpunct-class.md#numpunct__thousands_sep) détermine la séquence qui sépare les groupes de chiffres à gauche de la virgule décimale  
  
 Si aucun regroupement des contraintes n’imposées par **fac**. **regroupement** (le premier élément a la valeur CHAR_MAX), puis aucune instance de **fac**. `thousands_sep` sont générés dans le champ de résultat. Dans le cas contraire, les séparateurs sont insérés après la conversion d’impression.  
  
 La deuxième fonction membre virtuelle :  
  
```  
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,  
    CharType _Fill,
    unsigned long val) const;
```  
  
 se comporte comme la première, à ceci près qu’il remplace une spécification de conversion de **%ld** avec **lu**.  
  
 La troisième fonction membre virtuelle :  
  
```  
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,  
    CharType _Fill,
    double val) const;
```  
  
 se comporte comme la première, à ceci près qu’il génère un champ de sortie à virgule flottante de la valeur de **val**. **fac**. [decimal_point](../standard-library/numpunct-class.md#numpunct__decimal_point) détermine la séquence qui sépare les chiffres entiers les chiffres de fraction. La spécification de conversion d’impression équivalent est déterminée comme suit :  
  
-   Si **iosbase**. **indicateurs** & `ios_base::floatfield` == `ios_base::`[fixe](../Topic/%3Cios%3E%20functions.md#fixed), la spécification de conversion est **lf**.  
  
-   Si **iosbase**. **indicateurs** & **ios_base::floatfield** == `ios_base::`[scientifique](../Topic/%3Cios%3E%20functions.md#scientific), la spécification de conversion est `le`. Si **iosbase**. **indicateurs** & `ios_base::`[majuscules](../Topic/%3Cios%3E%20functions.md#uppercase) est différent de zéro, **e** est remplacé par **E**.  
  
-   Dans le cas contraire, la spécification de conversion est **lg**. Si **iosbase**. **indicateurs** & **ios_base::uppercase** est différent de zéro, **g** est remplacé par **G**.  
  
 Si **iosbase**. **indicateurs** & **ios_base::fixed** est différente de zéro ou si **iosbase**. [précision](../standard-library/ios-base-class.md#ios_base__precision) est supérieure à zéro, une précision avec la valeur **iosbase**. **précision** est ajouté à la spécification de conversion. Tout remplissage comporte de la même que pour un champ de sortie entier. Le caractère de remplissage est **remplissage**. Enfin :  
  
-   Si **iosbase**. **indicateurs** & `ios_base::`[showpos](../Topic/%3Cios%3E%20functions.md#showpos) est différent de zéro, l’indicateur **+** est ajouté à la spécification de conversion.  
  
-   Si **iosbase**. **indicateurs** & `ios_base::`[showpoint](../Topic/%3Cios%3E%20functions.md#showpoint) est différent de zéro, l’indicateur **#** est ajouté à la spécification de conversion.  
  
 La fonction membre virtuelle quatrième :  
  
```  
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,  
    CharType _Fill,
    long double val) const;
```  
  
 se comporte comme la troisième, à ceci près que le qualificateur **l** lors de la conversion spécification est remplacée par **L**.  
  
 La fonction membre virtuelle cinquième :  
  
```  
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,  
    CharType _Fill,
    const void* val) const;
```  
  
 se comporte comme la première, sauf que la spécification de conversion est `p`**,** ainsi que n’importe quel qualificateur nécessaire afin de spécifier la marge intérieure.  
  
 La fonction membre virtuelle sixième :  
  
```  
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,  
    CharType _Fill,
    bool val) const;
```  
  
 se comporte comme la première, sauf qu’elle génère un champ de sortie booléenne à partir de ` val`.  
  
 Un champ de sortie booléenne prend l’une des deux formes. Si **iosbase**. **indicateurs** & `ios_base::`[boolalpha](../Topic/%3Cios%3E%20functions.md#boolalpha) est **false**, la fonction membre retourne `do_put`(_ *Suivant*, \_ *Iosbase*, \_ *remplir*, ( **long**) ` val`), ce qui donne généralement une séquence générée soit 0 (pour **false**) ou 1 (pour **true**). Dans le cas contraire, la séquence générée est **fac**. [falsename](../standard-library/numpunct-class.md#numpunct__falsename)`)` (pour **false**), ou **fac**. [TrueName](../standard-library/numpunct-class.md#numpunct__truename) (pour **true**).  
  
 La fonction membre virtuelle septième :  
  
```  
virtual iter_type do_put(iter_type next,
    ios_base& iosbase,  
    Elem fill,
    long long val) const;
```  
  
 se comporte comme la première, à ceci près qu’il remplace une spécification de conversion de **%ld** avec **conception détaillée**.  
  
 La fonction membre virtuelle huitième :  
  
```  
virtual iter_type do_put(iter_type next,
    ios_base& iosbase,  
    Elem fill,
    unsigned long long val) const;
```  
  
 se comporte comme la première, à ceci près qu’il remplace une spécification de conversion de `ld` avec `llu`.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [put](#num_put__put), qui appelle la méthode `do_put`.  
  
##  <a name="a-namenumputitertypea-numputitertype"></a><a name="num_put__iter_type"></a>  num_put::iter_type  
 Type qui décrit un itérateur de sortie.  
  
```  
typedef OutputIterator iter_type;  
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme du paramètre de modèle **OutputIterator.**  
  
##  <a name="a-namenumputnumputa-numputnumput"></a><a name="num_put__num_put"></a>  num_put::num_put  
 Constructeur des objets de type `num_put`.  
  
```  
explicit num_put(size_t _Refs = 0);
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
  
 Le constructeur initialise les objets de base avec **paramètres régionaux ::**[facette](../standard-library/locale-class.md#facet_class)(_ *Refs*).  
  
##  <a name="a-namenumputputa-numputput"></a><a name="num_put__put"></a>  num_put::Put  
 Convertit un nombre en une séquence de **CharType**qui représente le nombre au format de paramètres régionaux donnés.  
  
```  
iter_type put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    bool val) const;

 
iter_type put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    long val) const;

 
iter_type put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    unsigned long val) const;

 
iter_type put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    Long long val) const;

 
iter_type put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    Unsigned long long val) const;

 
 
iter_type put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    double val) const;

 
iter_type put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    long double val) const;

 
iter_type put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    const void* val) const;
```  
  
### <a name="parameters"></a>Paramètres  
 ` dest`  
 Itérateur qui traite le premier élément de la chaîne insérée.  
  
 `_Iosbase`  
 Spécifié le flux qui contient des paramètres régionaux avec la facette numpunct utilisée pour les signes de ponctuation entre les indicateurs de mise en forme la sortie et de sortie.  
  
 `_Fill`  
 Un caractère qui est utilisé pour l’espacement.  
  
 ` val`  
 Le nombre ou type booléen qui est en sortie.  
  
### <a name="return-value"></a>Valeur de retour  
 Itérateur de sortie produits de la position située au-delà du dernier élément les adresses.  
  
### <a name="remarks"></a>Notes  
 Retournent toutes les fonctions membres [do_put](#num_put__do_put)( ` next`, `_Iosbase`, `_Fill`, ` val`).  
  
### <a name="example"></a>Exemple  
  
```  
// num_put_put.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "german_germany" );  
   basic_stringstream<char> psz2;  
   ios_base::iostate st = 0;  
   long double fVal;  
   cout << "The thousands separator is: "   
        << use_facet < numpunct <char> >(loc).thousands_sep( )   
        << endl;  
  
   psz2.imbue( loc );  
   use_facet < num_put < char > >  
      ( loc ).put(basic_ostream<char>::_Iter(psz2.rdbuf( ) ),  
                    psz2, ' ', fVal=1000.67);  
  
   if ( st & ios_base::failbit )  
      cout << "num_put( ) FAILED" << endl;  
   else  
      cout << "num_put( ) = " << psz2.rdbuf( )->str( ) << endl;  
}  
```  
  
```Output  
The thousands separator is: .  
num_put( ) = 1.000,67  
```  
  
## <a name="see-also"></a>Voir aussi  
 [\< paramètres régionaux>](../standard-library/locale.md)   
 [Facet, classe](../standard-library/locale-class.md#facet_class)   
 [Sécurité des threads dans la bibliothèque Standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)


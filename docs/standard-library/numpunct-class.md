---
title: "numpunct, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "xlocnum/std::numpunct"
  - "std::numpunct"
  - "numpunct"
  - "std.numpunct"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "numpunct (classe)"
ms.assetid: 73fb93cc-ac11-4c98-987c-bfa6267df596
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# numpunct, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Classe de modèle qui décrit un objet pouvant servir de facette locale pour décrire les séquences de type `CharType` utilisées pour représenter des informations sur la mise en forme et la ponctuation d'expressions numériques et booléennes.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <class CharType>  
class numpunct : public locale::facet;  
```  
  
#### <a name="parameters"></a>Paramètres  
 `CharType`  
 Type utilisé dans un programme pour encoder des caractères dans des paramètres régionaux spécifiques.  
  
## <a name="remarks"></a>Notes  
 Comme avec n'importe quelle facette de paramètres régionaux, l'ID d'objet statique possède une valeur stockée initiale de zéro. La première tentative d’accéder à sa valeur stockée stocke une valeur positive unique dans **id.**  
  
### <a name="constructors"></a>Constructeurs  
  
|||  
|-|-|  
|[numpunct](#numpunct__numpunct)|Constructeur des objets de type `numpunct`.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[char_type](#numpunct__char_type)|Type utilisé pour décrire un caractère utilisé par des paramètres régionaux.|  
|[STRING_TYPE](#numpunct__string_type)|Type qui décrit une chaîne contenant des caractères de type `CharType`.|  
  
### <a name="member-functions"></a>Fonctions membres  
  
|||  
|-|-|  
|[decimal_point](#numpunct__decimal_point)|Retourne un élément spécifique aux paramètres régionaux devant être utilisé comme séparateur décimal.|  
|[do_decimal_point](#numpunct__do_decimal_point)|Une fonction membre virtuelle est appelée pour renvoyer un élément spécifique aux paramètres régionaux devant être utilisé comme séparateur décimal.|  
|[do_falsename](#numpunct__do_falsename)|Une fonction membre virtuelle est appelée pour renvoyer une chaîne à utiliser comme représentation textuelle de la valeur `false`.|  
|[do_grouping](#numpunct__do_grouping)|Fonction membre virtuelle protégée appelée pour retourner une règle spécifique aux paramètres régionaux permettant de déterminer la manière dont les chiffres sont regroupés à gauche de la virgule décimale.|  
|[do_thousands_sep](#numpunct__do_thousands_sep)|Une fonction membre virtuelle est appelée pour renvoyer un élément spécifique aux paramètres régionaux devant être utilisé comme séparateur des milliers.|  
|[do_truename](#numpunct__do_truename)|Une fonction membre virtuelle est appelée pour renvoyer une chaîne à utiliser comme représentation textuelle de la valeur `true`.|  
|[falsename](#numpunct__falsename)|Retourne une chaîne à utiliser comme représentation textuelle de la valeur `false`.|  
|[regroupement](#numpunct__grouping)|Retourne une règle spécifique aux paramètres régionaux pour déterminer la manière dont les chiffres sont regroupés à gauche de la virgule décimale.|  
|[thousands_sep](#numpunct__thousands_sep)|Retourne un élément spécifique aux paramètres régionaux devant être utilisé comme séparateur des milliers.|  
|[TrueName](#numpunct__truename)|Retourne une chaîne à utiliser comme représentation textuelle de la valeur `true`.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \< paramètres régionaux>  
  
 **Espace de noms :** std  
  
##  <a name="a-namenumpunctchartypea-numpunctchartype"></a><a name="numpunct__char_type"></a>  numpunct::char_type  
 Type utilisé pour décrire un caractère utilisé par des paramètres régionaux.  
  
```  
typedef CharType char_type;  
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme du paramètre de modèle **CharType.**  
  
##  <a name="a-namenumpunctdecimalpointa-numpunctdecimalpoint"></a><a name="numpunct__decimal_point"></a>  numpunct::decimal_point  
 Retourne un élément spécifique aux paramètres régionaux devant être utilisé comme séparateur décimal.  
  
```  
CharType decimal_point() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un élément spécifique aux paramètres régionaux à utiliser comme séparateur décimal.  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne [do_decimal_point](#numpunct__do_decimal_point).  
  
### <a name="example"></a>Exemple  
  
```  
// numpunct_decimal_point.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "german_germany" );  
  
   const numpunct <char> &npunct =   
   use_facet <numpunct <char> >( loc);  
   cout << loc.name( ) << " decimal point "<<   
   npunct.decimal_point( ) << endl;  
   cout << loc.name( ) << " thousands separator "   
   << npunct.thousands_sep( ) << endl;  
};  
```  
  
```Output  
German_Germany.1252 decimal point ,  
German_Germany.1252 thousands separator .  
```  
  
##  <a name="a-namenumpunctdodecimalpointa-numpunctdodecimalpoint"></a><a name="numpunct__do_decimal_point"></a>  numpunct::do_decimal_point  
 Une fonction membre virtuelle est appelée pour renvoyer un élément spécifique aux paramètres régionaux devant être utilisé comme séparateur décimal.  
  
```  
virtual CharType do_decimal_point() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un élément spécifique aux paramètres régionaux à utiliser comme séparateur décimal.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [decimal_point](#numpunct__decimal_point), où la fonction membre virtuelle est appelée par `decimal_point`.  
  
##  <a name="a-namenumpunctdofalsenamea-numpunctdofalsename"></a><a name="numpunct__do_falsename"></a>  numpunct::do_falsename  
 La fonction membre virtuelle protégée retourne une séquence à utiliser comme une représentation textuelle de la valeur **false**.  
  
```  
virtual string_type do_falsename() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Chaîne contenant une séquence à utiliser comme une représentation textuelle de la valeur **false**.  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne la chaîne « false » pour représenter la valeur **false** dans tous les paramètres régionaux.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [falsename](#numpunct__falsename), où la fonction membre virtuelle est appelée par `falsename`.  
  
##  <a name="a-namenumpunctdogroupinga-numpunctdogrouping"></a><a name="numpunct__do_grouping"></a>  numpunct::do_grouping  
 Fonction membre virtuelle protégée appelée pour retourner une règle spécifique aux paramètres régionaux permettant de déterminer la manière dont les chiffres sont regroupés à gauche de la virgule décimale.  
  
```  
virtual string do_grouping() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une règle spécifique aux paramètres régionaux pour déterminer la manière dont les chiffres sont regroupés à gauche de la virgule décimale.  
  
### <a name="remarks"></a>Notes  
 Cette fonction membre virtuelle protégée retourne une règle spécifique aux paramètres régionaux permettant de déterminer la manière dont les chiffres sont regroupés à gauche de la virgule décimale. L’encodage est identique à celle de **lconv::grouping**.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [regroupement](#numpunct__grouping), où la fonction membre virtuelle est appelée par **regroupement**.  
  
##  <a name="a-namenumpunctdothousandssepa-numpunctdothousandssep"></a><a name="numpunct__do_thousands_sep"></a>  numpunct::do_thousands_sep  
 Une fonction membre virtuelle est appelée pour renvoyer un élément spécifique aux paramètres régionaux devant être utilisé comme séparateur des milliers.  
  
```  
virtual CharType do_thousands_sep() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne un élément spécifique aux paramètres régionaux devant être utilisé comme séparateur des milliers.  
  
### <a name="remarks"></a>Notes  
 La fonction membre virtuelle protégée retourne un élément spécifique de type **CharType** à utiliser comme séparateur de groupes à gauche de la virgule décimale.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [thousands_sep](#numpunct__thousands_sep), où la fonction membre virtuelle est appelée par `thousands_sep`.  
  
##  <a name="a-namenumpunctdotruenamea-numpunctdotruename"></a><a name="numpunct__do_truename"></a>  numpunct::do_truename  
 Fonction membre virtuelle est appelée pour retourner une chaîne à utiliser comme représentation textuelle de la valeur **true**.  
  
```  
virtual string_type do_truename() const;
```  
  
### <a name="remarks"></a>Notes  
 Une chaîne à utiliser comme représentation textuelle de la valeur **true**.  
  
 Une chaîne « true » pour représenter la valeur de retour de tous les paramètres régionaux **true**.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [truename](#numpunct__truename), où la fonction membre virtuelle est appelée par `truename`.  
  
##  <a name="a-namenumpunctfalsenamea-numpunctfalsename"></a><a name="numpunct__falsename"></a>  numpunct::falsename  
 Retourne une chaîne à utiliser comme représentation textuelle de la valeur **false**.  
  
```  
string_type falsename() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Chaîne qui contient une séquence de **CharType**s à utiliser comme une représentation textuelle de la valeur **false**.  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne la chaîne « false » pour représenter la valeur **false** dans tous les paramètres régionaux.  
  
 La fonction membre retourne [do_falsename](#numpunct__do_falsename).  
  
### <a name="example"></a>Exemple  
  
```  
// numpunct_falsename.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "English" );  
  
   const numpunct <char> &npunct = use_facet <numpunct <char> >( loc );  
   cout << loc.name( ) << " truename "<< npunct.truename( ) << endl;  
   cout << loc.name( ) << " falsename "<< npunct.falsename( ) << endl;  
  
   locale loc2( "French" );  
   const numpunct <char> &npunct2 = use_facet <numpunct <char> >(loc2);  
   cout << loc2.name( ) << " truename "<< npunct2.truename( ) << endl;  
   cout << loc2.name( ) << " falsename "<< npunct2.falsename( ) << endl;  
}  
```  
  
```Output  
English_United States.1252 truename true  
English_United States.1252 falsename false  
French_France.1252 truename true  
French_France.1252 falsename false  
```  
  
##  <a name="a-namenumpunctgroupinga-numpunctgrouping"></a><a name="numpunct__grouping"></a>  numpunct::GROUPING  
 Retourne une règle spécifique aux paramètres régionaux pour déterminer la manière dont les chiffres sont regroupés à gauche de la virgule décimale.  
  
```  
string grouping() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une règle spécifique aux paramètres régionaux pour déterminer la manière dont les chiffres sont regroupés à gauche de la virgule décimale.  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne [do_grouping](#numpunct__do_grouping).  
  
### <a name="example"></a>Exemple  
  
```  
// numpunct_grouping.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "german_germany");  
  
   const numpunct <char> &npunct =   
       use_facet < numpunct <char> >( loc );  
   for (unsigned int i = 0; i < npunct.grouping( ).length( ); i++)  
   {  
      cout << loc.name( ) << " international grouping:\n the "  
           << i <<"th group to the left of the radix character "  
           << "is of size " << (int)(npunct.grouping ( )[i])   
           << endl;  
   }  
}  
```  
  
```Output  
German_Germany.1252 international grouping:  
 the 0th group to the left of the radix character is of size 3  
```  
  
##  <a name="a-namenumpunctnumpuncta-numpunctnumpunct"></a><a name="numpunct__numpunct"></a>  numpunct::numpunct  
 Constructeur des objets de type `numpunct`.  
  
```  
explicit numpunct(size_t _Refs = 0);
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
  
##  <a name="a-namenumpunctstringtypea-numpunctstringtype"></a><a name="numpunct__string_type"></a>  numpunct::STRING_TYPE  
 Un type qui décrit une chaîne contenant des caractères de type **CharType**.  
  
```  
typedef basic_string<CharType, Traits, Allocator> string_type;  
```  
  
### <a name="remarks"></a>Notes  
 Type qui décrit une spécialisation de classe de modèle [basic_string](../standard-library/basic-string-class.md) dont les objets peuvent stocker des copies des séquences de signes de ponctuation.  
  
##  <a name="a-namenumpunctthousandssepa-numpunctthousandssep"></a><a name="numpunct__thousands_sep"></a>  numpunct::thousands_sep  
 Retourne un élément spécifique aux paramètres régionaux devant être utilisé comme séparateur des milliers.  
  
```  
CharType thousands_sep() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un élément spécifique aux paramètres régionaux à utiliser comme des milliers séparateur.  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne [do_thousands_sep](#numpunct__do_thousands_sep).  
  
### <a name="example"></a>Exemple  
  
```  
// numpunct_thou_sep.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "german_germany" );  
  
   const numpunct <char> &npunct =   
   use_facet < numpunct < char > >( loc );  
   cout << loc.name( ) << " decimal point "<<   
   npunct.decimal_point( ) << endl;  
   cout << loc.name( ) << " thousands separator "   
   << npunct.thousands_sep( ) << endl;  
};  
```  
  
```Output  
German_Germany.1252 decimal point ,  
German_Germany.1252 thousands separator .  
```  
  
##  <a name="a-namenumpuncttruenamea-numpuncttruename"></a><a name="numpunct__truename"></a>  numpunct::TrueName  
 Retourne une chaîne à utiliser comme représentation textuelle de la valeur **true**.  
  
```  
string_type falsename() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une chaîne à utiliser comme représentation textuelle de la valeur **true**.  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne [do_truename](#numpunct__do_truename).  
  
 Une chaîne « true » pour représenter la valeur de retour de tous les paramètres régionaux **true**.  
  
### <a name="example"></a>Exemple  
  
```  
// numpunct_truename.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "English" );  
  
   const numpunct < char> &npunct = use_facet <numpunct <char> >( loc );  
   cout << loc.name( ) << " truename "<< npunct.truename( ) << endl;  
   cout << loc.name( ) << " falsename "<< npunct.falsename( ) << endl;  
  
   locale loc2("French");  
   const numpunct <char> &npunct2 = use_facet <numpunct <char> >( loc2 );  
   cout << loc2.name( ) << " truename "<< npunct2.truename( ) << endl;  
   cout << loc2.name( ) << " falsename "<< npunct2.falsename( ) << endl;  
}  
```  
  
```Output  
English_United States.1252 truename true  
English_United States.1252 falsename false  
French_France.1252 truename true  
French_France.1252 falsename false  
```  
  
## <a name="see-also"></a>Voir aussi  
 [\< paramètres régionaux>](../standard-library/locale.md)   
 [Facet, classe](../standard-library/locale-class.md#facet_class)   
 [Sécurité des threads dans la bibliothèque Standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)


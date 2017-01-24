---
title: "locale, classe | Microsoft Docs"
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
  - "xlocale/std::locale"
  - "std::locale"
  - "std.locale"
  - "locale"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "locale (classe)"
ms.assetid: 7dd6d271-472d-4750-8fb5-ea8f55fbef62
caps.latest.revision: 28
caps.handback.revision: 28
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# locale, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Classe qui décrit un objet de paramètres régionaux encapsulant des informations spécifiques à la culture sous la forme d'un ensemble de facettes qui définissent collectivement un environnement localisé spécifique.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class locale;  
```  
  
## <a name="remarks"></a>Notes  
 Une facette est un pointeur vers un objet d’une classe dérivée de la classe [facette](#facet_class) qui contient un objet public du formulaire :  
  
```  
static locale::id id;  
```  
  
 Vous pouvez définir un ensemble ouvert de ces facettes. Vous pouvez également créer un objet de paramètres régionaux qui désigne un nombre arbitraire de facettes.  
  
 Les groupes prédéfinis de ces facettes représentent le [catégories de paramètres régionaux](#locale__category) traditionnellement gérées dans la bibliothèque C Standard par la fonction `setlocale`.  
  
 La catégorie collate (LC_COLLATE) comprend les facettes suivantes :  
  
```  
collate<char>  
collate<wchar_t>  
```  
  
 La catégorie ctype (LC_CTYPE) comprend les facettes suivantes :  
  
```  
ctype<char>  
ctype<wchar_t>  
codecvt<char, char, mbstate_t>  
codecvt<wchar_t, char, mbstate_t>  
codecvt<char16_t, char, mbstate_t>  
codecvt<char32_t, char, mbstate_t>  
```  
  
 La catégorie monetary (LC_MONETARY) comprend les facettes suivantes :  
  
```  
moneypunct<char, false>  
moneypunct<wchar_t, false>  
moneypunct<char, true>  
moneypunct<wchar_t, true>  
money_get<char, istreambuf_iterator<char>>  
money_get<wchar_t, istreambuf_iterator<wchar_t>>  
money_put<char, ostreambuf_iterator<char>>  
money_put<wchar_t, ostreambuf_iterator<wchar_t>>  
```  
  
 La catégorie numeric (LC_NUMERIC) comprend les facettes suivantes :  
  
```  
num_get<char, istreambuf_iterator<char>>  
num_get<wchar_t, istreambuf_iterator<wchar_t>>  
num_put<char, ostreambuf_iterator<char>>  
num_put<wchar_t, ostreambuf_iterator<wchar_t>>  
numpunct<char>  
numpunct<wchar_t>  
```  
  
 La catégorie time (LC_TIME) comprend les facettes suivantes :  
  
```  
time_get<char, istreambuf_iterator<char>>  
time_get<wchar_t, istreambuf_iterator<wchar_t>>  
time_put<char, ostreambuf_iterator<char>>  
time_put<wchar_t, ostreambuf_iterator<wchar_t>>  
```  
  
 La catégorie messages (LC_MESSAGES) comprend les facettes suivantes :  
  
```  
messages<char>  
messages<wchar_t>  
```  
  
 La dernière catégorie est requise par Posix, mais pas par le C standard.  
  
 Certaines de ces facettes prédéfinies sont utilisées par les classes iostreams pour contrôler la conversion des valeurs numériques en séquences de texte, et inversement.  
  
 Un objet de paramètres régionaux classe stocke également un nom de paramètres régionaux en tant qu’objet de classe [chaîne](../Topic/%3Cstring%3E%20typedefs.md#string). À l’aide d’un nom de paramètres régionaux non valide pour construire une facette de paramètres régionaux ou un objet de paramètres régionaux lève un objet de classe [runtime_error](../standard-library/runtime-error-class.md). Le nom de paramètres régionaux stocké est `"*"` si l'objet de paramètres régionaux ne peut pas avoir la garantie que les paramètres régionaux de style C correspondent exactement à ceux représentés par l'objet. Sinon, vous pouvez établir des paramètres régionaux correspondants dans la bibliothèque C Standard, pour l’objet de paramètres régionaux `_Loc`, en appelant `setlocale`(LC_ALL `,` `_Loc`. [nom](#locale__name)`().c_str()`).  
  
 Dans cette implémentation, vous pouvez également appeler la fonction membre statique :  
  
```  
static locale empty();
```  
  
 pour construire un objet de paramètres régionaux sans facette. Il est également de paramètres régionaux transparent. Si les fonctions de modèle [has_facet](../Topic/%3Clocale%3E%20functions.md#has_facet) et [use_facet](../Topic/%3Clocale%3E%20functions.md#use_facet) Impossible de trouver la facette demandée dans les paramètres régionaux transparents, elles consultent d’abord les paramètres régionaux globaux, puis, si c’est transparent, les paramètres régionaux classiques. Par conséquent, vous pouvez écrire :  
  
```  
cout.imbue(locale::empty());
```  
  
 Les insertions suivantes dans [cout](../Topic/%3Ciostream%3E%20functions.md#cout) sont atténuées par l’état actuel des paramètres régionaux globaux. Vous pouvez même écrire :  
  
```  
locale loc(locale::empty(),
    locale::classic(),  
    locale::numeric);

cout.imbue(loc);
```   
  
 Les règles de mise en forme numérique pour les insertions suivantes dans `cout` restent les mêmes que dans les paramètres régionaux du langage C, même lorsque les paramètres régionaux globaux fournissent des règles différentes d'insertion de dates et de valeurs monétaires.  
  
### <a name="constructors"></a>Constructeurs  
  
|||  
|-|-|  
|[paramètres régionaux](#locale__locale)|Crée des paramètres régionaux, une copie de paramètres régionaux ou une copie de paramètres régionaux où une facette ou une catégorie a été remplacée par une facette, ou une catégorie provenant d'autres paramètres régionaux.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[catégorie](#locale__category)|Type entier qui fournit des valeurs de masque de bits pour indiquer des familles de facettes standard.|  
  
### <a name="member-functions"></a>Fonctions membres  
  
|||  
|-|-|  
|[combiner](#locale__combine)|Insère une facette à partir des paramètres régionaux spécifiés dans les paramètres régionaux cibles.|  
|[nom](#locale__name)|Retourne le nom des paramètres régionaux stocké.|  
  
### <a name="static-functions"></a>Fonctions statiques  
  
|||  
|-|-|  
|[classique](#locale__classic)|La fonction membre statique retourne un objet de paramètres régionaux qui représente les paramètres régionaux classiques du langage C.|  
|[global](#locale__global)|Réinitialise les paramètres régionaux par défaut du programme.|  
  
### <a name="operators"></a>Opérateurs  
  
|||  
|-|-|  
|[opérateur ! =](#locale__operator_neq)|Vérifie l'inégalité de deux ensembles de paramètres régionaux.|  
|[Operator)](#locale__operator__)|Compare deux objets `basic_string`.|  
|[opérateur ==](#locale__operator_eq_eq)|Vérifie l'égalité de deux ensembles de paramètres régionaux.|  
  
### <a name="classes"></a>Classes  
  
|||  
|-|-|  
|[facette](#facet_class)|Classe qui sert de classe de base pour toutes les facettes de paramètres régionaux.|  
|[ID](#id_class)|La classe membre fournit un ID unique de facette utilisé comme index pour rechercher les facettes de paramètres régionaux.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \< paramètres régionaux>  
  
 **Espace de noms :** std  
  
##  <a name="a-namelocalecategorya-localecategory"></a><a name="locale__category"></a>  locale::Category  
 Type entier qui fournit des valeurs de masque de bits pour indiquer des familles de facettes standard.  
  
```  
typedef int category;  
static const int collate = LC_COLLATE;  
static const int ctype = LC_CTYPE;  
static const int monetary = LC_MONETARY;  
static const int numeric = LC_NUMERIC;  
static const int time = LC_TIME;  
static const int messages = LC_MESSAGES;  
static const int all = LC_ALL;  
static const int none = 0;  
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme pour une `int` type qui peut représenter un groupe d’éléments distincts de masque de bits tapez local aux paramètres régionaux de classe ou peut être utilisé pour représenter toutes les catégories de paramètres régionaux C correspondantes. Les éléments sont :  
  
- **Collate**, qui correspond à la catégorie C LC_COLLATE  
  
- **CType**, qui correspond à la catégorie C LC_CTYPE  
  
- **monétaire**, qui correspond à la catégorie C LC_MONETARY  
  
- **numérique**, qui correspond à la catégorie C LC_NUMERIC  
  
- **temps**, qui correspond à la catégorie C LC_TIME  
  
- **messages**, qui correspond à la catégorie Posix LC_MESSAGES  
  
 En outre, les deux valeurs utiles sont :  
  
- **aucun**, qui correspond à aucune des catégories C  
  
- **tous les**, qui correspond à l’union C de toutes les catégories LC_ALL  
  
 Vous pouvez représenter un groupe de catégories arbitraire à l’aide de `OR` avec ces constantes, comme dans **monétaires** &#124 ; **temps**.  
  
##  <a name="a-namelocaleclassica-localeclassic"></a><a name="locale__classic"></a>  locale::Classic  
 La fonction membre statique retourne un objet de paramètres régionaux qui représente les paramètres régionaux classiques du langage C.  
  
```  
static const locale& classic();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Référence aux paramètres régionaux C.  
  
### <a name="remarks"></a>Notes  
 Les paramètres régionaux C classique sont aux États-Unis Paramètres régionaux de ASCII en anglais dans la bibliothèque C Standard qui est implicitement utilisé dans les programmes qui ne sont pas internationalisées.  
  
### <a name="example"></a>Exemple  
  
```  
// locale_classic.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <string>  
#include <locale>  
  
using namespace std;  
  
int main( )   
{  
   locale loc1( "german" );  
   locale loc2 = locale::global( loc1 );  
   cout << "The name of the previous locale is: " << loc2.name( )  
        << "." << endl;  
   cout << "The name of the current locale is: " << loc1.name( )   
        << "." << endl;  
  
   if (loc2 == locale::classic( ) )  
      cout << "The previous locale was classic." << endl;  
   else  
      cout << "The previous locale was not classic." << endl;  
  
   if (loc1 == locale::classic( ) )  
      cout << "The current locale is classic." << endl;  
   else  
      cout << "The current locale is not classic." << endl;  
}  
```  
  
```Output  
The name of the previous locale is: C.  
The name of the current locale is: German_Germany.1252.  
The previous locale was classic.  
The current locale is not classic.  
```  
  
##  <a name="a-namelocalecombinea-localecombine"></a><a name="locale__combine"></a>  locale::combine  
 Insère une facette à partir des paramètres régionaux spécifiés dans les paramètres régionaux cibles.  
  
```  
template <class Facet>  
locale combine(const locale& _Loc) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `_Loc`  
 Les paramètres régionaux qui contient la facette à insérer dans les paramètres régionaux cibles.  
  
### <a name="return-value"></a>Valeur de retour  
 La fonction membre retourne un objet de paramètres régionaux qui remplace ou ajoute à **\*cela** la facette `Facet` répertoriés dans `_Loc`.  
  
### <a name="example"></a>Exemple  
  
```  
// locale_combine.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <tchar.h>  
using namespace std;  
  
int main() {  
   locale loc ( "German_germany" );  
   _TCHAR * s1 = _T("Das ist wei\x00dfzz."); // \x00df is the German sharp-s; it comes before z in the German alphabet  
   _TCHAR * s2 = _T("Das ist weizzz.");  
   int result1 = use_facet<collate<_TCHAR> > ( loc ).  
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );  
   cout << isalpha (_T ( '\x00df' ), loc ) << result1 << endl;  
  
   locale loc2 ( "C" );  
   int result2 = use_facet<collate<_TCHAR> > ( loc2 ).  
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );  
   cout << isalpha (_T ( '\x00df' ), loc2 )  << result2 << endl;  
  
   locale loc3 = loc2.combine<collate<_TCHAR> > (loc);  
   int result3 = use_facet<collate<_TCHAR> > ( loc3 ).  
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );  
   cout << isalpha (_T ( '\x00df' ), loc3 ) << result3 << endl;  
}  
```  
  
##  <a name="a-namefacetclassa-facet-class"></a><a name="facet_class"></a>  Facet, classe  
 Classe qui sert de classe de base pour toutes les facettes de paramètres régionaux.  
  
facette de la classe {protégés : facette explicite (size_t _Refs = 0) ; virtuel ~ facet() ; private : facet(const facet&) / / non défini opérateur void =(const facet&) / / non défini} ;  
  
### <a name="remarks"></a>Notes  
 Notez que vous ne pouvez pas copier ou assigner un objet de facette de la classe. Vous pouvez créer et détruire les objets dérivés de la classe `locale::facet` mais pas les objets de la classe de base appropriée. En règle générale, vous construisez un objet `_Myfac` dérivée de facette lorsque vous construisez des paramètres régionaux, comme dans **localeloc**( `locale::classic`(), **nouveau**`_Myfac`) ;  
  
 Dans ce cas, le constructeur de facette de la classe de base doit avoir une valeur zéro `_Refs` argument. Lorsque l’objet n’est plus nécessaire, elle est supprimée. Par conséquent, vous fournissez un zéro _ *Refs* argument uniquement dans les rares cas où vous prenez la responsabilité de la durée de vie de l’objet.  
  
##  <a name="a-namelocaleglobala-localeglobal"></a><a name="locale__global"></a>  locale::global  
 Réinitialise les paramètres régionaux par défaut pour le programme. Cela affecte les paramètres régionaux globaux pour C et C++.  
  
```  
static locale global(const locale& _Loc);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Loc`  
 Les paramètres régionaux à utiliser en tant que les paramètres régionaux par défaut par le programme.  
  
### <a name="return-value"></a>Valeur de retour  
 Les précédent paramètres régionaux avant que les paramètres régionaux par défaut a été réinitialisé.  
  
### <a name="remarks"></a>Notes  
 Au démarrage du programme, les paramètres régionaux globaux sont le même que les paramètres régionaux classiques. Le `global()` les appels de fonction `setlocale( LC_ALL, loc.name. c_str())` pour établir des paramètres régionaux correspondants dans la bibliothèque C Standard.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// locale_global.cpp  
// compile by using: /EHsc  
#include <locale>  
#include <iostream>  
#include <tchar.h>  
using namespace std;  
  
int main( )  
{  
   locale loc ( "German_germany" );  
   locale loc1;  
   cout << "The initial locale is: " << loc1.name( ) << endl;  
   locale loc2 = locale::global ( loc );  
   locale loc3;  
   cout << "The current locale is: " << loc3.name( ) << endl;  
   cout << "The previous locale was: " << loc2.name( ) << endl;  
}  
```  
  
```Output  
The initial locale is: C  
The current locale is: German_Germany.1252  
The previous locale was: C  
```  
  
##  <a name="a-nameidclassa-id-class"></a><a name="id_class"></a>  ID de classe  
 La classe membre fournit un ID unique de facette utilisé comme index pour rechercher les facettes de paramètres régionaux.  
  
id de classe {protégés : id() ; private : id(const id&) / / non défini opérateur void =(const id&) / / non défini} ;  
  
### <a name="remarks"></a>Notes  
 La classe membre décrit l’objet de membre statique requis par chaque facette de paramètres régionaux unique. Notez que vous ne peut pas copier ou assigner un objet de classe **id**.  
  
##  <a name="a-namelocalelocalea-localelocale"></a><a name="locale__locale"></a>  locale::locale  
 Crée des paramètres régionaux, une copie de paramètres régionaux ou une copie de paramètres régionaux où une facette ou une catégorie a été remplacée par une facette, ou une catégorie provenant d'autres paramètres régionaux.  
  
```  
locale();

explicit locale(
    const char* _Locname,  
    category _Cat = all);

explicit locale(
    const string& _Locname);

locale(
    const locale& _Loc);

locale(
    const locale& _Loc,   
    const locale& _Other,  
    category _Cat);

locale(
    const locale& _Loc,   
    const char* _Locname,  
    category _Cat);

template <class Facet>  
locale(
 const locale& _Loc,   
    const Facet* _Fac);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Locname`  
 Nom de paramètres régionaux.  
  
 `_Loc`  
 Paramètres régionaux qui sera copié lors de la construction les nouveaux paramètres régionaux.  
  
 `_Other`  
 Paramètres régionaux à partir de laquelle sélectionner une catégorie.  
  
 `_Cat`  
 La catégorie à être substituées dans les paramètres régionaux construit.  
  
 `_Fac`  
 La facette à être substituées dans les paramètres régionaux construit.  
  
### <a name="remarks"></a>Notes  
 Le premier constructeur initialise l’objet pour faire correspondre les paramètres régionaux globaux. Les deuxième et troisièmes constructeurs initialisent toutes les catégories de paramètres régionaux pour avoir un comportement cohérent avec le nom des paramètres régionaux `_Locname`. Copient les autres constructeurs `_Loc`, avec les exceptions notées :  
  
 `locale(const locale& _Loc, const locale& _Other, category _Cat);`  
  
 remplace de `_Other` ces facettes correspondant à une catégorie C pour le C & `_Cat` est différente de zéro.  
  
 `locale(const locale& _Loc, const char* _Locname, category _Cat);`  
  
 `locale(const locale& _Loc, const string& _Locname, category _Cat);`  
  
 remplace de `locale(_Locname, _All)` ces facettes correspondant à une catégorie C pour le C & `_Cat`est différente de zéro.  
  
 `template<class Facet> locale(const locale& _Loc, Facet* _Fac);`  
  
 remplace dans (ou ajoute) `_Loc` la facette `_Fac`, Si `_Fac` n’est pas un pointeur null.  
  
 Si le nom de paramètres régionaux `_Locname` est un pointeur null ou non valide, la fonction lève [runtime_error](../standard-library/runtime-error-class.md).  
  
### <a name="example"></a>Exemple  
  
```  
// locale_locale.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <tchar.h>  
using namespace std;  
  
int main( ) {  
  
   // Second constructor  
   locale loc ( "German_germany" );  
   _TCHAR * s1 = _T("Das ist wei\x00dfzz."); // \x00df is the German sharp-s, it comes before z in the German alphabet  
   _TCHAR * s2 = _T("Das ist weizzz.");  
   int result1 = use_facet<collate<_TCHAR> > ( loc ).  
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );  
   cout << isalpha (_T ( '\x00df' ), loc ) << result1 << endl;  
  
   // The first (default) constructor  
   locale loc2;  
   int result2 = use_facet<collate<_TCHAR> > ( loc2 ).  
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );  
   cout << isalpha (_T ( '\x00df' ), loc2 )  << result2 << endl;  
  
   // Third constructor  
   locale loc3 (loc2,loc, _M_COLLATE );  
   int result3 = use_facet<collate<_TCHAR> > ( loc3 ).  
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );  
   cout << isalpha (_T ( '\x00df' ), loc3 ) << result3 << endl;  
  
   // Fourth constructor  
   locale loc4 (loc2, "German_Germany", _M_COLLATE );  
   int result4 = use_facet<collate<_TCHAR> > ( loc4 ).  
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );  
   cout << isalpha (_T ( '\x00df' ), loc4 ) << result4 << endl;  
}  
```  
  
##  <a name="a-namelocalenamea-localename"></a><a name="locale__name"></a>  locale::Name  
 Retourne le nom des paramètres régionaux stocké.  
  
```  
string name() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Chaîne indiquant le nom des paramètres régionaux.  
  
### <a name="example"></a>Exemple  
  
```  
// locale_name.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <string>  
#include <locale>  
  
using namespace std;  
  
int main( )   
{  
   locale loc1( "german" );  
   locale loc2 = locale::global( loc1 );  
   cout << "The name of the previous locale is: "   
        << loc2.name( ) << "." << endl;  
   cout << "The name of the current locale is: "   
        << loc1.name( ) << "." << endl;  
}  
```  
  
```Output  
The name of the previous locale is: C.  
The name of the current locale is: German_Germany.1252.  
```  
  
##  <a name="a-namelocaleoperatorneqa-localeoperator"></a><a name="locale__operator_neq"></a>  locale::operator ! =  
 Vérifie l'inégalité de deux ensembles de paramètres régionaux.  
  
```  
bool operator!=(const locale& right) const;
```  
  
### <a name="parameters"></a>Paramètres  
 ` right`  
 Un des paramètres régionaux à tester pour vérifier leur inégalité.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur booléenne qui est **true** si les paramètres régionaux ne sont pas des copies des même paramètres régionaux ; **false** si les paramètres régionaux sont des copies des même paramètres régionaux.  
  
### <a name="remarks"></a>Notes  
 Deux paramètres régionaux est égales si elles sont les mêmes paramètres régionaux, si une est une copie de l’autre, ou s’ils ont des noms identiques.  
  
### <a name="example"></a>Exemple  
  
```  
// locale_op_ne.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <string>  
#include <locale>  
  
using namespace std;  
  
int main( )   
{  
   locale loc1( "German_Germany" );  
   locale loc2( "German_Germany" );  
   locale loc3( "English" );  
  
   if ( loc1 != loc2 )  
      cout << "locales loc1 (" << loc1.name( )  
      << ") and\n loc2 (" << loc2.name( ) << ") are not equal." << endl;  
   else  
      cout << "locales loc1 (" << loc1.name( )  
      << ") and\n loc2 (" << loc2.name( ) << ") are equal." << endl;  
  
   if ( loc1 != loc3 )  
      cout << "locales loc1 (" << loc1.name( )  
      << ") and\n loc3 (" << loc3.name( ) << ") are not equal." << endl;  
   else  
      cout << "locales loc1 (" << loc1.name( )  
      << ") and\n loc3 (" << loc3.name( ) << ") are equal." << endl;  
}  
```  
  
```Output  
locales loc1 (German_Germany.1252) and  
 loc2 (German_Germany.1252) are equal.  
locales loc1 (German_Germany.1252) and  
 loc3 (English_United States.1252) are not equal.  
```  
  
##  <a name="a-namelocaleoperatora-localeoperator"></a><a name="locale__operator__"></a>  locale ::operator()  
 Compare deux objets `basic_string`.  
  
```  
template <class CharType, class Traits, class Allocator>  
bool operator()(
    const basic_string<CharType, Traits, Allocator>& left,  
    const basic_string<CharType, Traits, Allocator>& right) const;
```  
  
### <a name="parameters"></a>Paramètres  
 ` left`  
 La chaîne de gauche.  
  
 ` right`  
 La chaîne de droite.  
  
### <a name="return-value"></a>Valeur de retour  
 La fonction membre retourne :  
  
-   -1 si la première séquence compare inférieure à la deuxième séquence.  
  
-   + 1 si la deuxième séquence compare inférieure à la première séquence.  
  
-   0 si les séquences sont équivalentes.  
  
### <a name="remarks"></a>Notes  
 La fonction membre est exécutée :  
  
```  
const collate<CharType>& fac = use_fac<collate<CharType>>(*this);

return (fac.compare(left.begin(), left.end(), right.begin(), right.end()) <0);
```  
  
 Par conséquent, vous pouvez utiliser un objet de paramètres régionaux comme un objet de fonction.  
  
### <a name="example"></a>Exemple  
  
```  
// locale_op_compare.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <string>  
#include <locale>  
  
int main( )   
{  
   using namespace std;  
   wchar_t *sa = L"ztesting";  
   wchar_t *sb = L"\0x00DFtesting";  
   basic_string<wchar_t> a( sa );  
   basic_string<wchar_t> b( sb );  
  
   locale loc( "German_Germany" );  
   cout << loc( a,b ) << endl;  
  
   const collate<wchar_t>& fac = use_facet<collate<wchar_t> >( loc );  
   cout << ( fac.compare( sa, sa + a.length( ),  
       sb, sb + b.length( ) ) < 0) << endl;  
}  
```  
  
```Output  
0  
0  
```  
  
##  <a name="a-namelocaleoperatoreqeqa-localeoperator"></a><a name="locale__operator_eq_eq"></a>  locale::operator ==  
 Vérifie l'égalité de deux ensembles de paramètres régionaux.  
  
```  
bool operator==(const locale& right) const;
```  
  
### <a name="parameters"></a>Paramètres  
 ` right`  
 Un des paramètres régionaux à tester l’égalité.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur booléenne qui est **true** si les paramètres régionaux sont des copies des même paramètres régionaux ; **false** si les paramètres régionaux ne sont pas des copies des même paramètres régionaux.  
  
### <a name="remarks"></a>Notes  
 Deux paramètres régionaux est égales si elles sont les mêmes paramètres régionaux, si une est une copie de l’autre, ou s’ils ont des noms identiques.  
  
### <a name="example"></a>Exemple  
  
```  
// locale_op_eq.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <string>  
#include <locale>  
  
using namespace std;  
  
int main( )   
{  
   locale loc1( "German_Germany" );  
   locale loc2( "German_Germany" );  
   locale loc3( "English" );  
  
   if ( loc1 == loc2 )  
      cout << "locales loc1 (" << loc1.name( )  
      << ")\n and loc2 (" << loc2.name( ) << ") are equal."   
      << endl;  
   else  
      cout << "locales loc1 (" << loc1.name( )  
      << ")\n and loc2 (" << loc2.name( ) << ") are not equal."   
      << endl;  
  
   if ( loc1 == loc3 )  
      cout << "locales loc1 (" << loc1.name( )  
      << ")\n and loc3 (" << loc3.name( ) << ") are equal."   
      << endl;  
   else  
      cout << "locales loc1 (" << loc1.name( )  
      << ")\n and loc3 (" << loc3.name( ) << ") are not equal."   
      << endl;  
}  
```  
  
```Output  
locales loc1 (German_Germany.1252)  
 and loc2 (German_Germany.1252) are equal.  
locales loc1 (German_Germany.1252)  
 and loc3 (English_United States.1252) are not equal.  
```  
  
## <a name="see-also"></a>Voir aussi  
 [\< paramètres régionaux>](../standard-library/locale.md)   
 [Pages de codes](../c-runtime-library/code-pages.md)   
 [Noms de paramètres régionaux, les langues et les chaînes de pays/région](../c-runtime-library/locale-names-languages-and-country-region-strings.md)   
 [Sécurité des threads dans la bibliothèque Standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)


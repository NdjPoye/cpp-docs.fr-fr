---
title: "codecvt, classe | Microsoft Docs"
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
  - "codecvt"
  - "std::codecvt"
  - "std.codecvt"
  - "xlocale/std::codecvt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "codecvt (classe)"
ms.assetid: 37d3efa1-2b7f-42b6-b04f-7a972c8c2c86
caps.latest.revision: 23
caps.handback.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# codecvt, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Classe de modèle qui décrit un objet pouvant servir de facette de paramètres régionaux. Elle peut contrôler les conversions d'une séquence de valeurs utilisées pour encoder des caractères au sein du programme en une séquence de valeurs utilisées pour encoder des caractères en dehors du programme.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <class CharType, class Byte, class StateType>  
class codecvt : public locale::facet, codecvt_base;  
```  
  
#### <a name="parameters"></a>Paramètres  
 `CharType`  
 Type utilisé dans le cadre d'un programme pour encoder des caractères.  
  
 `Byte`  
 Type utilisé pour encoder des caractères en dehors d'un programme.  
  
 `StateType`  
 Type qui peut être utilisé pour représenter les états intermédiaires d'une conversion entre types internes et types externes de représentations de caractères.  
  
## <a name="remarks"></a>Notes  
 La classe de modèle décrit un objet pouvant servir un [facette de paramètres régionaux](../standard-library/locale-class.md#facet_class), pour contrôler les conversions entre une séquence de valeurs de type `CharType` et une séquence de valeurs de type `Byte`. La classe `StateType` caractérise la transformation. Un objet de la classe `StateType` stocke toute information d'état nécessaire lors d'une conversion.  
  
 L'encodage interne utilise une représentation avec un nombre fixe d'octets par caractère, généralement de type `char` ou `wchar_t`.  
  
 Comme avec n'importe quelle facette de paramètres régionaux, l'objet statique `id` possède une valeur stockée initiale de zéro. La première tentative d’accéder à sa valeur stockée stocke une valeur positive unique dans `id`.  
  
 Les versions de modèles de [do_in](#codecvt__do_in) et [do_out](#codecvt__do_out) retournent toujours `codecvt_base::noconv`.  
  
 La bibliothèque C++ standard définit plusieurs spécialisations explicites :  
  
 `template<>`  
  
 `codecvt<wchar_t, char, mbstate_t>`  
  
 effectue des conversions entre des séquences `wchar_t` et `char`.  
  
 `template<>`  
  
 `codecvt<char16_t, char, mbstate_t>`  
  
 effectue des conversions entre des séquences `char16_t` encodées au format UTF-16 et des séquences `char` encodées au format UTF-8.  
  
 `template<>`  
  
 `codecvt<char32_t, char, mbstate_t>`  
  
 effectue des conversions entre des séquences `char32_t` encodées au format UTF-32 (UCS-4) et des séquences `char` encodées au format UTF-8.  
  
### <a name="constructors"></a>Constructeurs  
  
|||  
|-|-|  
|[codecvt](#codecvt__codecvt)|Constructeur d'objets de la classe `codecvt` qui sert de facette de paramètres régionaux pour la gestion des conversions.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[extern_type](#codecvt__extern_type)|Type de caractère utilisé pour les représentations externes.|  
|[intern_type](#codecvt__intern_type)|Type de caractère utilisé pour les représentations internes.|  
|[state_type](#codecvt__state_type)|Type de caractère utilisé pour représenter les états intermédiaires lors de conversions entre des représentations internes et externes.|  
  
### <a name="member-functions"></a>Fonctions membres  
  
|||  
|-|-|  
|[always_noconv](#codecvt__always_noconv)|Vérifie si une conversion doit être effectuée.|  
|[do_always_noconv](#codecvt__do_always_noconv)|Fonction virtuelle appelée pour vérifier si une conversion doit être effectuée.|  
|[do_encoding](#codecvt__do_encoding)|Fonction virtuelle qui vérifie si l'encodage du flux `Byte` dépend d'un état. Elle vérifie également si le rapport entre les `Byte` utilisés et les `CharType` produits est constant, et, le cas échéant, détermine la valeur de ce rapport.|  
|[do_in](#codecvt__do_in)|Fonction virtuelle appelée pour convertir une séquence de `Byte` internes en une séquence de `CharType` externes.|  
|[do_length](#codecvt__do_length)|Fonction virtuelle qui détermine le nombre de `Byte` d'une séquence donnée de d'`Byte` externes n'ayant pas produit plus d'un nombre donné de d'`CharType` internes, et retourne ce nombre de `Byte`.|  
|[do_max_length](#codecvt__do_max_length)|Fonction virtuelle qui retourne le nombre maximal d'octets externes nécessaires pour produire un `CharType` interne.|  
|[do_out](#codecvt__do_out)|Fonction virtuelle appelée pour convertir une séquence de `CharType` internes en une séquence d'octets externes.|  
|[do_unshift](#codecvt__do_unshift)|Fonction virtuelle appelée pour fournir le `Byte` nécessaire dans une conversion avec dépendance d'état, afin d'ajouter le dernier caractère d'une séquence de `Byte`.|  
|[encodage](#codecvt__encoding)|Vérifie si l'encodage du flux `Byte` dépend d'un état. Elle vérifie également si le rapport entre les `Byte` utilisés et les `CharType` produits est constant, et, le cas échéant, détermine la valeur de ce rapport.|  
|[dans](#codecvt__in)|Convertit la représentation externe d'une séquence de `Byte` en la représentation interne d'une séquence de `CharType`.|  
|[longueur](#codecvt__length)|Détermine le nombre de `Byte` d'une séquence donnée de d'`Byte` externes n'ayant pas produit plus d'un nombre donné de d'`CharType` internes, et retourne ce nombre de `Byte`.|  
|[max_length](#codecvt__max_length)|Retourne le nombre maximal de `Byte` externes nécessaires pour produire un `CharType` interne.|  
|[sortie](#codecvt__out)|Convertit une séquence de `CharType` internes en une séquence de `Byte` externes.|  
|[unshift](#codecvt__unshift)|Fournit les `Byte` externes nécessaires pour une conversion avec dépendance d'état, afin d'ajouter le dernier caractère de la séquence de `Byte`.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \< paramètres régionaux>  
  
 **Espace de noms :** std  
  
##  <a name="a-namecodecvtalwaysnoconva-codecvtalwaysnoconv"></a><a name="codecvt__always_noconv"></a>  codecvt::always_noconv  
 Vérifie si une conversion doit être effectuée.  
  
```  
bool always_noconv() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur booléenne qui est **true** Si la conversion doit être effectuée ; **false** est au moins doit être effectuée.  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne [do_always_noconv](#codecvt__do_always_noconv).  
  
### <a name="example"></a>Exemple  
  
```  
// codecvt_always_noconv.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
using namespace std;  
  
int main( )     
{  
   locale loc ( "German_Germany" );  
   bool result1 = use_facet<codecvt<char, char, mbstate_t> >   
      ( loc ).always_noconv( );  
  
   if ( result1 )  
      cout << "No conversion is needed." << endl;  
   else  
      cout << "At least one conversion is required." << endl;  
  
   bool result2 = use_facet<codecvt<wchar_t, char, mbstate_t> >   
      ( loc ).always_noconv( );  
  
   if ( result2 )  
      cout << "No conversion is needed." << endl;  
   else  
      cout << "At least one conversion is required." << endl;  
}  
```  
  
```Output  
No conversion is needed.  
At least one conversion is required.  
```  
  
##  <a name="a-namecodecvtcodecvta-codecvtcodecvt"></a><a name="codecvt__codecvt"></a>  codecvt::codecvt  
 Le constructeur pour les objets de la classe codecvt qui sert de facette de paramètres régionaux pour la gestion des conversions.  
  
```  
explicit codecvt(size_t _Refs = 0);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Refs`  
 Valeur entière qui sert à spécifier le type de gestion de la mémoire pour l’objet.  
  
### <a name="remarks"></a>Notes  
 Les valeurs possibles pour le `_Refs` paramètre et leur signification sont :  
  
-   0 : la durée de vie de l’objet est gérée par les paramètres régionaux qui le contiennent.  
  
-   1 : la durée de vie de l’objet doit être gérée manuellement.  
  
-   \> 0 : ces valeurs ne sont pas définis.  
  
 Le constructeur initialise sa `locale::facet` objet de base avec **paramètres régionaux ::**[facette](../standard-library/locale-class.md#facet_class)( `_Refs`) *.*  
  
##  <a name="a-namecodecvtdoalwaysnoconva-codecvtdoalwaysnoconv"></a><a name="codecvt__do_always_noconv"></a>  codecvt::do_always_noconv  
 Fonction virtuelle appelée pour vérifier si une conversion doit être effectuée.  
  
```  
virtual bool do_always_noconv() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 La fonction membre virtuelle protégée retourne **true** uniquement si chaque appel à [do_in](#codecvt__do_in) ou [do_out](#codecvt__do_out) retourne **noconv**.  
  
 La version du modèle retourne toujours **true**.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [always_noconv](#codecvt__always_noconv), qui appelle la méthode `do_always_noconv`.  
  
##  <a name="a-namecodecvtdoencodinga-codecvtdoencoding"></a><a name="codecvt__do_encoding"></a>  codecvt::do_encoding  
 Une fonction virtuelle qui vérifie si le codage de la **octets** flux est dépend d’un état si le rapport entre la **octets**utilisé et le **CharType**produits est constant et, le cas échéant, détermine la valeur de ce rapport.  
  
```  
virtual int do_encoding() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 La fonction membre virtuelle protégée retourne :  
  
-   -1, si le codage de séquences de type `extern_type` dépend de l’état.  
  
-   0 si l’encodage implique des séquences de longueur variable.  
  
- *N*, si le codage n'implique que les séquences de longueur *N*  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [codage](#codecvt__encoding), qui appelle la méthode `do_encoding`.  
  
##  <a name="a-namecodecvtdoina-codecvtdoin"></a><a name="codecvt__do_in"></a>  codecvt::do_in  
 Une fonction virtuelle appelée pour convertir une séquence d’externe **octets**en une séquence interne **CharType**s.  
  
```  
virtual result do_in(
    StateType& _State,  
    const Byte* first1,   
    const Byte* last1,   
    const Byte*& next1,  
    CharType* first2,  
    CharType* last2,  
    CharType*& next2,) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `_State`  
 L’état de conversion qui est conservé entre les appels à la fonction membre.  
  
 ` first1`  
 Pointeur vers le début de la séquence à convertir.  
  
 ` last1`  
 Pointeur vers la fin de la séquence à convertir.  
  
 ` next1`  
 Pointeur au delà de la fin de la séquence convertie, le premier caractère non converti.  
  
 ` first2`  
 Pointeur vers le début de la séquence converti.  
  
 ` last2`  
 Pointeur vers la fin de la séquence convertie.  
  
 ` next2`  
 Pointeur vers le **CharType** qui vient après le dernier converti **CharType**, du premier caractère non modifiés dans la séquence de destination.  
  
### <a name="return-value"></a>Valeur de retour  
 Un retour qui indique la réussite, réussite partielle ou Échec de l’opération. La fonction renvoie :  
  
- **codecvt_base::Error** Si la séquence source est malade formée.  
  
- `codecvt_base::noconv` Si la fonction n’effectue aucun conversion.  
  
- **codecvt_base::OK** Si la conversion réussit.  
  
- **codecvt_base::Partial** Si la source est insuffisante ou si la destination n’est pas assez grande, pour que la conversion réussisse.  
  
### <a name="remarks"></a>Notes  
 `_State` doit représenter l’état de la conversion initiale au début d’une nouvelle séquence source. La fonction modifie sa valeur stockée que nécessaire pour refléter l’état actuel d’une conversion réussie. Sa valeur stockée dans le cas contraire est non spécifiée.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [dans](#codecvt__in), qui appelle la méthode `do_in`.  
  
##  <a name="a-namecodecvtdolengtha-codecvtdolength"></a><a name="codecvt__do_length"></a>  codecvt::do_length  
 Une fonction virtuelle qui détermine combien **octets**à partir d’une séquence donnée d’externes **octets**s produisent pas plus qu’un nombre donné d’interne **CharType**s et retourne le nombre de **octets**s.  
  
```  
virtual int do_length(
    const StateType& _State,  
    const Byte* first1,   
    const Byte* last1,  
    size_t _Len2) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `_State`  
 L’état de conversion qui est conservé entre les appels à la fonction membre.  
  
 ` first1`  
 Pointeur vers le début de la séquence externe.  
  
 ` last1`  
 Pointeur vers la fin de la séquence externe.  
  
 `_Len2`  
 Le nombre maximal de **octets**s qui peuvent être retournées par la fonction membre.  
  
### <a name="return-value"></a>Valeur de retour  
 Entier qui représente le nombre maximal de conversions, inférieure ou égale à `_Len2`, défini par la séquence source externe à [ ` first1`, ` last1`).  
  
### <a name="remarks"></a>Notes  
 La fonction membre virtuelle protégée appelle en fait `do_in`( `_State`, ` first1`, ` last1`, ` next1`, `_Buf`, `_Buf` + `_Len2`, ` next2`) pour `_State` (une copie de l’état), une mémoire tampon `_Buf`, ainsi que des pointeurs ` next1`et ` next2`.  
  
 Elle retourne ensuite ` next2` – **buf**. Par conséquent, il compte le nombre de conversions, inférieure ou égale à `_Len2`, défini par la séquence source à [ ` first1`, ` last1`).  
  
 La version du modèle retourne toujours le plus petit de ` last1` – ` first1` et `_Len2`.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [longueur](#codecvt__length), qui appelle la méthode **do_length**.  
  
##  <a name="a-namecodecvtdomaxlengtha-codecvtdomaxlength"></a><a name="codecvt__do_max_length"></a>  codecvt::do_max_length  
 Une fonction virtuelle qui retourne le nombre maximal d’externes **octets**s nécessaires pour produire un interne **CharType**.  
  
```  
virtual int do_max_length() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre maximal de **octets**s nécessaires pour produire un **CharType**.  
  
### <a name="remarks"></a>Notes  
 La fonction membre virtuelle protégée retourne la plus grande valeur possible qui peut être retournée par [do_length](#codecvt__do_length)( ` first1`, ` last1`, 1) pour les valeurs valides arbitraires de ` first1` et ` last1`.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [max_length](#codecvt__max_length), qui appelle la méthode `do_max_length`.  
  
##  <a name="a-namecodecvtdoouta-codecvtdoout"></a><a name="codecvt__do_out"></a>  codecvt::do_out  
 Une fonction virtuelle appelée pour convertir une séquence interne **CharType**en une séquence d’externes **octets**s.  
  
```  
virtual result do_out(
    StateType& _State,  
    const CharType* first1,   
    const CharType* last1,  
    const CharType*& next1,  
    Byte* first2,   
    Byte* last2,   
    Byte*& next2) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `_State`  
 L’état de conversion qui est conservé entre les appels à la fonction membre.  
  
 ` first1`  
 Pointeur vers le début de la séquence à convertir.  
  
 ` last1`  
 Pointeur vers la fin de la séquence à convertir.  
  
 ` next1`  
 Référence à un pointeur vers le premier non converti **CharType**, après la dernière **CharType** converti.  
  
 ` first2`  
 Pointeur vers le début de la séquence converti.  
  
 ` last2`  
 Pointeur vers la fin de la séquence convertie.  
  
 ` next2`  
 Référence à un pointeur vers le premier non converti **octets**, après la dernière **octets** converti.  
  
### <a name="return-value"></a>Valeur de retour  
 La fonction renvoie :  
  
- **codecvt_base::Error** Si la séquence source est malade formée.  
  
- `codecvt_base::noconv` Si la fonction n’effectue aucun conversion.  
  
- **codecvt_base::OK** Si la conversion réussit.  
  
- **codecvt_base::Partial** Si la source est insuffisante ou si la destination n’est pas assez grande pour que la conversion réussisse.  
  
### <a name="remarks"></a>Notes  
 `_State` doit représenter l’état de la conversion initiale au début d’une nouvelle séquence source. La fonction modifie sa valeur stockée que nécessaire pour refléter l’état actuel d’une conversion réussie. Sa valeur stockée dans le cas contraire est non spécifiée.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [en](#codecvt__out), qui appelle la méthode `do_out`.  
  
##  <a name="a-namecodecvtdounshifta-codecvtdounshift"></a><a name="codecvt__do_unshift"></a>  codecvt::do_unshift  
 Une fonction virtuelle appelée pour fournir les **octets**nécessaires dépendent de la conversion pour terminer le dernier caractère dans une séquence de **octets**s.  
  
```  
virtual result do_unshift(
    StateType& _State,  
    Byte* first2,   
    Byte* last2,   
    Byte*& next2) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `_State`  
 L’état de conversion qui est conservé entre les appels à la fonction membre.  
  
 ` first2`  
 Pointeur vers la première position dans la plage de destination.  
  
 ` last2`  
 Pointeur vers la dernière position dans la plage de destination.  
  
 ` next2`  
 Pointeur vers le premier élément modifié dans la séquence de destination.  
  
### <a name="return-value"></a>Valeur de retour  
 La fonction renvoie :  
  
- **codecvt_base::Error** Si _ *état* représente un état non valide  
  
- `codecvt_base::noconv` Si la fonction n’effectue aucun conversion  
  
- **codecvt_base::OK** Si la conversion réussit  
  
- **codecvt_base::Partial** Si la destination n’est pas assez grande pour que la conversion réussisse  
  
### <a name="remarks"></a>Notes  
 La fonction membre virtuelle protégée tente de convertir l’élément source **CharType**(0) à une séquence de destination qu’elle stocke dans [ ` first2`, ` last2`), à l’exception de l’élément de fin **octets**(0). Il stocke toujours dans ` next2` un pointeur vers le premier élément modifié dans la séquence de destination.  
  
 _ *État* doit représenter l’état de la conversion initiale au début d’une nouvelle séquence source. La fonction modifie sa valeur stockée que nécessaire pour refléter l’état actuel d’une conversion réussie. En règle générale, conversion de l’élément source **CharType**(0) quitte l’état actuel de l’état de la conversion initiale.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [unshift](#codecvt__unshift), qui appelle la méthode `do_unshift`.  
  
##  <a name="a-namecodecvtencodinga-codecvtencoding"></a><a name="codecvt__encoding"></a>  codecvt::Encoding  
 Vérifie si le codage de la **octets** flux est dépend d’un état si le rapport entre la **octets**utilisé et le **CharType**produits est constant et, le cas échéant, détermine la valeur de ce rapport.  
  
```  
int encoding() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Si la valeur de retour est positive, cette valeur est le nombre constant de **octets** caractères requis pour produire le **CharType** caractère.  
  
 La fonction membre virtuelle protégée retourne :  
  
-   -1, si le codage de séquences de type `extern_type` dépend de l’état.  
  
-   0 si l’encodage implique des séquences de longueur variable.  
  
- *N*, si le codage n'implique que les séquences de longueur *N.*  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne [do_encoding](#codecvt__do_encoding).  
  
### <a name="example"></a>Exemple  
  
```  
// codecvt_encoding.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
using namespace std;  
  
int main( )     
{  
   locale loc ( "German_Germany" );  
   int result1 = use_facet<codecvt<char, char, mbstate_t> > ( loc ).encoding ( );  
   cout << result1 << endl;  
   result1 = use_facet<codecvt<wchar_t, char, mbstate_t> > ( loc ).encoding( );  
   cout << result1 << endl;  
   result1 = use_facet<codecvt<char, wchar_t, mbstate_t> > ( loc ).encoding( );  
   cout << result1 << endl;  
}  
```  
  
```Output  
1  
1  
1  
```  
  
##  <a name="a-namecodecvtexterntypea-codecvtexterntype"></a><a name="codecvt__extern_type"></a>  codecvt::extern_type  
 Type de caractère utilisé pour les représentations externes.  
  
```  
typedef Byte extern_type;  
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme du paramètre de modèle **octets**.  
  
##  <a name="a-namecodecvtina-codecvtin"></a><a name="codecvt__in"></a>  codecvt::in  
 Convertit la représentation externe d’une séquence de **octets**en la représentation interne d’une séquence de **CharType**s.  
  
```  
result in(
    StateType& _State,  
    const Byte* first1,   
    const Byte* last1,   
    const Byte*& next1,  
    CharType* first2,  
    CharType* last2,  
    CharType*& next2,) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `_State`  
 L’état de conversion qui est conservé entre les appels à la fonction membre.  
  
 ` first1`  
 Pointeur vers le début de la séquence à convertir.  
  
 ` last1`  
 Pointeur vers la fin de la séquence à convertir.  
  
 ` next1`  
 Pointeur au delà de la fin de la séquence convertie le premier caractère non converti.  
  
 ` first2`  
 Pointeur vers le début de la séquence converti.  
  
 ` last2`  
 Pointeur vers la fin de la séquence convertie.  
  
 ` next2`  
 Pointeur vers le **CharType** qui vient après le dernier converti **Chartype** du premier caractère non modifiés dans la séquence de destination.  
  
### <a name="return-value"></a>Valeur de retour  
 Un retour qui indique la réussite, la réussite partielle ou l’échec de l’opération. La fonction renvoie :  
  
- **codecvt_base::Error** Si la séquence source est malade formée.  
  
- `codecvt_base::noconv` Si la fonction n’effectue aucun conversion.  
  
- **codecvt_base::OK** Si la conversion réussit.  
  
- **codecvt_base::Partial** Si la source est insuffisante ou si la destination n’est pas assez grande pour que la conversion réussisse.  
  
### <a name="remarks"></a>Notes  
 `_State` doit représenter l’état de la conversion initiale au début d’une nouvelle séquence source. La fonction modifie sa valeur stockée, en fonction des besoins, afin de refléter l’état actuel d’une conversion réussie. Après une conversion partielle, `_State` doit être définie afin de permettre la conversion de reprendre à l’arrivée de nouveaux caractères.  
  
 La fonction membre retourne [do_in](#codecvt__do_in)( `_State`, _ *First1, nom1, next1, First2, _Llast2, next2*).  
  
### <a name="example"></a>Exemple  
  
```  
// codecvt_in.cpp  
// compile with: /EHsc  
#define _INTL  
#include <locale>  
#include <iostream>  
using namespace std;  
#define LEN 90  
int main( )     
{  
   char* pszExt = "This is the string to be converted!";  
   wchar_t pwszInt [LEN+1];  
   memset(&pwszInt[0], 0, (sizeof(wchar_t))*(LEN+1));  
   const char* pszNext;  
   wchar_t* pwszNext;  
   mbstate_t state = {0};  
   locale loc("C");//English_Britain");//German_Germany  
   int res = use_facet<codecvt<wchar_t, char, mbstate_t> >  
     ( loc ).in( state,  
          pszExt, &pszExt[strlen(pszExt)], pszNext,  
          pwszInt, &pwszInt[strlen(pszExt)], pwszNext );  
   pwszInt[strlen(pszExt)] = 0;  
   wcout << ( (res!=codecvt_base::error)  L"It worked! " : L"It didn't work! " )  
   << L"The converted string is:\n ["  
   << &pwszInt[0]  
   << L"]" << endl;  
   exit(-1);  
}  
```  
  
```Output  
It worked! The converted string is:  
 [This is the string to be converted!]  
```  
  
##  <a name="a-namecodecvtinterntypea-codecvtinterntype"></a><a name="codecvt__intern_type"></a>  codecvt::intern_type  
 Type de caractère utilisé pour les représentations internes.  
  
```  
typedef CharType intern_type;  
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme du paramètre de modèle **CharType**.  
  
##  <a name="a-namecodecvtlengtha-codecvtlength"></a><a name="codecvt__length"></a>  codecvt::Length  
 Détermine combien **octets**à partir d’une séquence donnée d’externes **octets**s produisent pas plus qu’un nombre donné d’interne **CharType**s et retourne le nombre de **octets**s.  
  
```  
int length(
    const StateType& _State,  
    const Byte* first1,   
    const Byte* last1,  
    size_t _Len2) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `_State`  
 L’état de conversion qui est conservé entre les appels à la fonction membre.  
  
 ` first1`  
 Pointeur vers le début de la séquence externe.  
  
 ` last1`  
 Pointeur vers la fin de la séquence externe.  
  
 `_Len2`  
 Le nombre maximal d’octets qui peuvent être retournées par la fonction membre.  
  
### <a name="return-value"></a>Valeur de retour  
 Entier qui représente le nombre maximal de conversions, inférieure ou égale à `_Len2`, défini par la séquence source externe à [ ` first1`, ` last1`).  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne [do_length](#codecvt__do_length)( *_State, first1*, ` last1`, `_Len2`).  
  
### <a name="example"></a>Exemple  
  
```  
// codecvt_length.cpp  
// compile with: /EHsc  
#define _INTL  
#include <locale>  
#include <iostream>  
using namespace std;  
#define LEN 90  
int main( )     
{  
   char* pszExt = "This is the string whose length is to be measured!";  
   mbstate_t state = {0};  
   locale loc("C");//English_Britain");//German_Germany  
   int res = use_facet<codecvt<wchar_t, char, mbstate_t> >  
     ( loc ).length( state,  
          pszExt, &pszExt[strlen(pszExt)], LEN );  
   cout << "The length of the string is: ";  
   wcout << res;  
   cout << "." << endl;  
   exit(-1);  
}  
```  
  
```Output  
The length of the string is: 50.  
```  
  
##  <a name="a-namecodecvtmaxlengtha-codecvtmaxlength"></a><a name="codecvt__max_length"></a>  codecvt::max_length  
 Retourne le nombre maximal d’externes **octets**s nécessaires pour produire un interne **CharType**.  
  
```  
int max_length() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre maximal de **octets**s nécessaires pour produire un **CharType**.  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne [do_max_length](#codecvt__do_max_length).  
  
### <a name="example"></a>Exemple  
  
```  
// codecvt_max_length.cpp  
// compile with: /EHsc  
#define _INTL  
#include <locale>  
#include <iostream>  
using namespace std;  
  
int main( )     
{  
   locale loc( "C");//English_Britain" );//German_Germany  
   int res = use_facet<codecvt<char, char, mbstate_t> >  
     ( loc ).max_length( );  
   wcout << res << endl;  
}  
```  
  
```Output  
1  
```  
  
##  <a name="a-namecodecvtouta-codecvtout"></a><a name="codecvt__out"></a>  codecvt::out  
 Convertit une séquence interne **CharType**en une séquence d’externes **octets**s.  
  
```  
result out(
    StateType& _State,  
    const CharType* first1,   
    const CharType* last1,  
    const CharType*& next1,  
    Byte* first2,   
    Byte* last2,   
    Byte*& next2) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `_State`  
 L’état de conversion qui est conservé entre les appels à la fonction membre.  
  
 ` first1`  
 Pointeur vers le début de la séquence à convertir.  
  
 ` last1`  
 Pointeur vers la fin de la séquence à convertir.  
  
 ` next1`  
 Référence à un pointeur vers le premier non converti **CharType** après la dernière **CharType** converti.  
  
 ` first2`  
 Pointeur vers le début de la séquence converti.  
  
 ` last2`  
 Pointeur vers la fin de la séquence convertie.  
  
 ` next2`  
 Référence à un pointeur vers le premier non converti **octets** après la dernière converti **octets**.  
  
### <a name="return-value"></a>Valeur de retour  
 La fonction membre retourne [do_out](#codecvt__do_out)( `_State`, ` first1`, ` last1`, ` next1`, ` first2`, ` last2`, ` next2`).  
  
### <a name="remarks"></a>Notes  
 Pour plus d’informations, consultez [codecvt::do_out](#codecvt__do_out).  
  
### <a name="example"></a>Exemple  
  
```  
// codecvt_out.cpp  
// compile with: /EHsc  
#define _INTL  
#include <locale>  
#include <iostream>  
#include <wchar.h>  
using namespace std;  
#define LEN 90  
int main( )     
{  
   char pszExt[LEN+1];  
   wchar_t *pwszInt = L"This is the wchar_t string to be converted.";  
   memset( &pszExt[0], 0, ( sizeof( char ) )*( LEN+1 ) );  
   char* pszNext;  
   const wchar_t* pwszNext;  
   mbstate_t state;  
   locale loc("C");//English_Britain");//German_Germany  
   int res = use_facet<codecvt<wchar_t, char, mbstate_t> >  
      ( loc ).out( state,  
      pwszInt, &pwszInt[wcslen( pwszInt )], pwszNext ,  
      pszExt, &pszExt[wcslen( pwszInt )], pszNext );  
   pszExt[wcslen( pwszInt )] = 0;  
   cout << ( ( res!=codecvt_base::error )  "It worked: " : "It didn't work: " )  
   << "The converted string is:\n ["  
   << &pszExt[0]  
   << "]" << endl;  
}  
```  
  
```Output  
It worked: The converted string is:  
 [This is the wchar_t string to be converted.]  
```  
  
##  <a name="a-namecodecvtstatetypea-codecvtstatetype"></a><a name="codecvt__state_type"></a>  codecvt::state_type  
 Type de caractère utilisé pour représenter les états intermédiaires lors de conversions entre des représentations internes et externes.  
  
```  
typedef StateType state_type;  
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme du paramètre de modèle **StateType**.  
  
##  <a name="a-namecodecvtunshifta-codecvtunshift"></a><a name="codecvt__unshift"></a>  codecvt::unshift  
 Fournit le **octet**nécessaires dépendent de la conversion pour terminer le dernier caractère dans une séquence de **octets**s.  
  
```  
result unshift(
    StateType& _State,  
    Byte* first2,   
    Byte* last2,   
    Byte*& next2) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `_State`  
 L’état de conversion qui est conservé entre les appels à la fonction membre.  
  
 ` first2`  
 Pointeur vers la première position dans la plage de destination.  
  
 ` last2`  
 Pointeur vers la dernière position dans la plage de destination.  
  
 ` next2`  
 Pointeur vers le premier élément modifié dans la séquence de destination.  
  
### <a name="return-value"></a>Valeur de retour  
 La fonction renvoie :  
  
- **codecvt_base::Error** Si l’état représente un état non valide.  
  
- `codecvt_base::noconv` Si la fonction n’effectue aucun conversion.  
  
- **codecvt_base::OK** Si la conversion réussit.  
  
- **codecvt_base::Partial** Si la destination n’est pas assez grande pour que la conversion réussisse.  
  
### <a name="remarks"></a>Notes  
 La fonction membre virtuelle protégée tente de convertir l’élément source **CharType**(0) à une séquence de destination qu’elle stocke dans [ ` first2`, ` last2`), à l’exception de l’élément de fin **octets**(0). Il stocke toujours dans ` next2` un pointeur vers le premier élément modifié dans la séquence de destination.  
  
 `_State` doit représenter l’état de la conversion initiale au début d’une nouvelle séquence source. La fonction modifie sa valeur stockée, en fonction des besoins, afin de refléter l’état actuel d’une conversion réussie. En règle générale, conversion de l’élément source **CharType**(0) quitte l’état actuel de l’état de la conversion initiale.  
  
 La fonction membre retourne [do_unshift](#codecvt__do_unshift)( `_State`, ` first2`, ` last2`, ` next2` ).  
  
## <a name="see-also"></a>Voir aussi  
 [\< paramètres régionaux>](../standard-library/locale.md)   
 [Pages de codes](../c-runtime-library/code-pages.md)   
 [Noms de paramètres régionaux, les langues et les chaînes de pays/région](../c-runtime-library/locale-names-languages-and-country-region-strings.md)   
 [Sécurité des threads dans la bibliothèque Standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)


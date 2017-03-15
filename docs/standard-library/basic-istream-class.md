---
title: basic_istream, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- basic_istream
- istream/std::basic_istream
- std::basic_istream
- std.basic_istream
dev_langs:
- C++
helpviewer_keywords:
- basic_istream class
ms.assetid: c7c27111-de6d-42b4-95a3-a7e65259bf17
caps.latest.revision: 21
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
ms.sourcegitcommit: 85c900f2263ae1c1089478badc85388e3b5e8548
ms.openlocfilehash: 32308d4cd6a3cc1409f04958dde8dad9204718bc
ms.lasthandoff: 02/24/2017

---
# <a name="basicistream-class"></a>basic_istream, classe
Décrit un objet qui contrôle l’extraction d’éléments et d’objets codés à partir d’une mémoire tampon de flux avec des éléments de type `Elem`, également appelé [char_type](../standard-library/basic-ios-class.md#basic_ios__char_type), dont les caractéristiques sont déterminées par la classe *Tr*, également appelée [traits_type](../standard-library/basic-ios-class.md#basic_ios__traits_type).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <class Elem, class Tr = char_traits<Elem>>  
class basic_istream : virtual public basic_ios<Elem, Tr>  
```  
  
## <a name="remarks"></a>Notes  
 La plupart des fonctions membres qui surchargent [operator>>](#basic_istream__operator_gt__gt_) sont des fonctions d’entrée mises en forme. Elles suivent le modèle :  
  
```cpp  
iostate state = goodbit;
const sentry ok(*this);

if (ok)
{
    try
    {
        /*extract elements and convert
            accumulate flags in state.
            store a successful conversion*/
    }
    catch (...)
    {
        try
        {
            setstate(badbit);

        }
        catch (...)
        {
        }
        if ((exceptions()& badbit) != 0)
            throw;
    }
}
setstate(state);

return (*this);
```  
  
 De nombreuses autres fonctions membres sont des fonctions d'entrée non mise en forme. Elles suivent le modèle :  
  
```cpp  
iostate state = goodbit;
count = 0;    // the value returned by gcount  
const sentry ok(*this, true);

if (ok)
{
    try
    {
        /* extract elements and deliver
            count extracted elements in count
            accumulate flags in state */
    }
    catch (...)
    {
        try
        {
            setstate(badbit);

        }
        catch (...)
        {
        }
        if ((exceptions()& badbit) != 0)
            throw;
    }
}
setstate(state);
```  
  
 Les deux groupes de fonctions appellent [setstate](../standard-library/basic-ios-class.md#basic_ios__setstate)( **eofbit**) s’ils rencontrent la fin du fichier lors de l’extraction d’éléments.  
  
 Un objet de la classe `basic_istream`< `Elem`, *Tr*> stocke :  
  
-   Un objet de base public virtuel de la classe [basic_ios](../standard-library/basic-ios-class.md)< `Elem`, *Tr*> `.`  
  
-   Nombre d’extractions pour la dernière opération d’entrée non mise en forme (appelé **count** dans le code précédent).  
  
## <a name="example"></a>Exemple  
 Consultez l’exemple de [basic_ifstream, classe](../standard-library/basic-ifstream-class.md) pour en savoir plus sur les flux d’entrée.  
  
### <a name="constructors"></a>Constructeurs  
  
|||  
|-|-|  
|[basic_istream](#basic_istream__basic_istream)|Construit un objet de type `basic_istream`.|  
  
### <a name="member-functions"></a>Fonctions membres  
  
|||  
|-|-|  
|[gcount](#basic_istream__gcount)|Retourne le nombre de caractères lus au cours de la dernière entrée non mise en forme.|  
|[get](#basic_istream__get)|Lit un ou plusieurs caractères dans le flux d'entrée.|  
|[getline](#basic_istream__getline)|Lit une ligne dans le flux d'entrée.|  
|[ignore](#basic_istream__ignore)|Ignore un certain nombre d'éléments à partir de la position de lecture actuelle.|  
|[peek](#basic_istream__peek)|Retourne le caractère suivant à lire.|  
|[putback](#basic_istream__putback)|Place un caractère spécifié dans le flux.|  
|[read](#basic_istream__read)|Lit un nombre spécifié de caractères dans le flux et les stocke dans un tableau.|  
|[readsome](#basic_istream__readsome)|Lire seulement dans la mémoire tampon.|  
|[seekg](#basic_istream__seekg)|Déplace la position de lecture dans un flux.|  
|[sentry](#basic_istream__sentry)|La classe imbriquée décrit un objet dont la déclaration structure les fonctions d'entrée mise en forme et les fonctions d'entrée non mise en forme.|  
|[swap](#basic_istream__swap)|Échange cet objet `basic_istream` pour le paramètre d'objet `basic_istream` fourni.|  
|[sync](#basic_istream__sync)|Synchronise le périphérique d’entrée associé au flux avec la mémoire tampon du flux.|  
|[tellg](#basic_istream__tellg)|Indique la position de lecture actuelle dans le flux.|  
|[unget](#basic_istream__unget)|Replace le dernier caractère lu dans le flux.|  
  
### <a name="operators"></a>Opérateurs  
  
|||  
|-|-|  
|[operator>>](#basic_istream__operator_gt__gt_)|Appelle une fonction sur le flux d'entrée ou lit les données mises en forme dans le flux d'entrée.|  
|[operator=](#basic_istream__operator_eq)|Affecte le `basic_istream` du côté droit de l'opérateur à cet objet. Il s'agit d'une assignation de déplacement qui implique une référence `rvalue` qui ne laisse pas de copie.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<istream>  
  
 **Espace de noms :** std  
  
##  <a name="a-namebasicistreambasicistreama--basicistreambasicistream"></a><a name="basic_istream__basic_istream"></a>  basic_istream::basic_istream  
 Construit un objet de type `basic_istream`.  
  
```  
explicit basic_istream(
    basic_streambuf<Elem, Tr>* strbuf,  
    bool _Isstd = false);

basic_istream(basic_istream&& right);
```  
  
### <a name="parameters"></a>Paramètres  
 ` strbuf`  
 Objet de type [basic_streambuf](../standard-library/basic-streambuf-class.md).  
  
 `_Isstd`  
 `true` s’il s’agit d’un flux standard ; sinon, `false`.  
  
 ` right`  
 Objet `basic_istream` à copier.  
  
### <a name="remarks"></a>Notes  
 Le premier constructeur initialise la classe de base en appelant [init](../standard-library/basic-ios-class.md#basic_ios__init)(_S`trbuf`). Il stocke également zéro dans le nombre d’extractions. Pour plus d’informations sur ce nombre d’extractions, consultez la section Notes de la rubrique de présentation [basic_istream, classe](../standard-library/basic-istream-class.md).  
  
 Le deuxième constructeur initialise la classe de base en appelant `move``( right)`. Il stocke également _R `ight.gcount()` dans le nombre d’extractions et stocke zéro dans le nombre d’extractions pour _R `ight`.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [basic_ifstream::basic_ifstream](../standard-library/basic-ifstream-class.md#basic_ifstream__basic_ifstream) pour en savoir plus sur les flux d’entrée.  
  
##  <a name="a-namebasicistreamgcounta--basicistreamgcount"></a><a name="basic_istream__gcount"></a>  basic_istream::gcount  
 Retourne le nombre de caractères lus au cours de la dernière entrée non mise en forme.  
  
```  
streamsize gcount() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Nombre d’extractions.  
  
### <a name="remarks"></a>Notes  
 Utilisez [basic_istream::get](#basic_istream__get) pour lire les caractères sans mise en forme.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// basic_istream_gcount.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
int main( )   
{  
   cout << "Type the letter 'a': ";  
  
   ws( cin );  
   char c[10];  
  
   cin.get( &c[0],9 );  
   cout << c << endl;  
  
   cout << cin.gcount( ) << endl;  
}  
```  
  
```Output  
  
a  
  
```  
  
```Output  
  
      aType the letter 'a':  
a  
1  
```  
  
##  <a name="a-namebasicistreamgeta--basicistreamget"></a><a name="basic_istream__get"></a>  basic_istream::get  
 Lit un ou plusieurs caractères dans le flux d'entrée.  
  
```  
int_type get();

basic_istream<Elem, Tr>& get(Elem& Ch);
basic_istream<Elem, Tr>& get(Elem* str, streamsize count);
basic_istream<Elem, Tr>& get(Elem* str, streamsize count, Elem Delim);

basic_istream<Elem, Tr>& get(basic_streambuf<Elem, Tr>& strbuf);
basic_istream<Elem, Tr>& get(basic_streambuf<Elem, Tr>& strbuf, Elem Delim);
```  
  
### <a name="parameters"></a>Paramètres  
 ` count`  
 Nombre de caractères à lire à partir de `strbuf`.  
  
 `Delim`  
 Caractère qui doit arrêter la lecture s’il se trouve avant ` count`.  
  
 ` str`  
 Chaîne dans laquelle écrire.  
  
 `Ch`  
 Caractère à obtenir.  
  
 ` strbuf`  
 Mémoire tampon dans laquelle écrire.  
  
### <a name="return-value"></a>Valeur de retour  
 La forme sans paramètre de get retourne l’élément lu comme un entier ou la fin du fichier. Les autres formes retournent le flux (* `this`).  
  
### <a name="remarks"></a>Notes  
 La première de ces fonctions d’entrée sans mise en forme extrait un élément, si possible, en retournant `rdbuf`-> `sbumpc`. Sinon, elle retourne **traits_type::**[eof](../standard-library/char-traits-struct.md#char_traits__eof). Si la fonction n’extrait aucun élément, elle appelle [setstate](../standard-library/basic-ios-class.md#basic_ios__setstate)( **failbit**).  
  
 La deuxième fonction extrait l’élément [int_type](../standard-library/basic-ios-class.md#basic_ios__int_type) `meta` de la même manière. Si la valeur de `meta` est égale à **traits_type::eof**, la fonction appelle `setstate`( **failbit**). Sinon, elle stocke **traits_type::**[to_char_type](../standard-library/char-traits-struct.md#char_traits__to_char_type)( `meta`) dans `Ch`. La fonction retourne **\*this**.  
  
 La troisième fonction retourne **get**(_ *Str*, ` count`, `widen`(’\ **n**’)).  
  
 La quatrième fonction extrait jusqu’à ` count` - 1 éléments et les stocke dans le tableau en commençant par _ *Str*. Elle stocke toujours `char_type` après les éléments extraits qu’elle stocke. Pour les besoins du test, l’extraction s’arrête :  
  
-   À la fin du fichier.  
  
-   Une fois que la fonction a extrait un élément dont la valeur est égale à `Delim`. Dans ce cas, l’élément est remis dans la séquence contrôlée.  
  
-   Une fois que la fonction a extrait ` count` - 1 éléments.  
  
 Si la fonction n’extrait aucun élément, elle appelle `setstate`( **failbit**). Dans tous les cas, elle retourne **\*this**.  
  
 La cinquième fonction retourne **get**( **strbuf**, `widen`(’\ **n**’)).  
  
 La sixième fonction extrait des éléments et les insère dans **strbuf**. L’extraction s’arrête à la fin du fichier ou sur un élément dont la valeur est égale à _ *Delim,* qui n’est pas extrait. Elle s’arrête également, sans extraire l’élément en question, si une insertion échoue ou lève une exception (qui est interceptée, mais n’est pas levée à nouveau). Si la fonction n’extrait aucun élément, elle appelle `setstate`( **failbit**). Dans tous les cas, la fonction retourne **\*this**.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// basic_istream_get.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
int main( )   
{  
   char c[10];  
  
   c[0] = cin.get( );  
   cin.get( c[1] );  
   cin.get( &c[2],3 );  
   cin.get( &c[4], 4, '7' );  
  
   cout << c << endl;  
}  
```  
  
```Output  
  
1111  
```  
  
##  <a name="a-namebasicistreamgetlinea--basicistreamgetline"></a><a name="basic_istream__getline"></a>  basic_istream::getline  
 Obtient une ligne du flux d’entrée.  
  
```  
basic_istream<Elem, Tr>& getline(
    char_type* str,   
    streamsize count);

basic_istream<Elem, Tr>& getline(
    char_type* str,   
    streamsize count,   
    char_type Delim);
```  
  
### <a name="parameters"></a>Paramètres  
 ` count`  
 Nombre de caractères à lire à partir de **strbuf**.  
  
 `Delim`  
 Caractère qui doit arrêter la lecture s’il se trouve avant ` count`.  
  
 ` str`  
 Chaîne dans laquelle écrire.  
  
### <a name="return-value"></a>Valeur de retour  
 Le flux ( **\*this**).  
  
### <a name="remarks"></a>Notes  
 La première de ces fonctions d’entrée sans mise en forme retourne **getline**(_ *Str*, ` count`, `widen`(’ `\`**n**’)).  
  
 La deuxième fonction extrait jusqu’à ` count` - 1 éléments et les stocke dans le tableau en commençant par _ *Str*. Elle stocke toujours le caractère de fin de chaîne après tous les éléments extraits qu’elle stocke. Pour les besoins du test, l’extraction s’arrête :  
  
-   À la fin du fichier.  
  
-   Une fois que la fonction a extrait un élément dont la valeur est égale à `Delim`. Dans ce cas, l’élément n’est ni remis à sa place, ni ajouté à la séquence contrôlée.  
  
-   Une fois que la fonction a extrait ` count` - 1 éléments.  
  
 Si la fonction n’extrait aucun élément ou extrait ` count` - 1 éléments, elle appelle [setstate](../standard-library/basic-ios-class.md#basic_ios__setstate)( **failbit**). Dans tous les cas, elle retourne **\*this**.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// basic_istream_getline.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
int main( )   
{  
   char c[10];  
  
   cin.getline( &c[0], 5, '2' );  
   cout << c << endl;  
}  
```  
  
```Output  
  
121  
```  
  
##  <a name="a-namebasicistreamignorea--basicistreamignore"></a><a name="basic_istream__ignore"></a>  basic_istream::ignore  
 Ignore un certain nombre d'éléments à partir de la position de lecture actuelle.  
  
```  
basic_istream<Elem, Tr>& ignore(
    streamsize count = 1,  
    int_type Delim = traits_type::eof());
```  
  
### <a name="parameters"></a>Paramètres  
 ` count`  
 Nombre d’éléments à ignorer à partir de la position de lecture actuelle.  
  
 `Delim`  
 Élément qui, si rencontré avant count, oblige **ignore** à retourner et autoriser tous les éléments après `Delim` à lire.  
  
### <a name="return-value"></a>Valeur de retour  
 Le flux ( **\*this**).  
  
### <a name="remarks"></a>Notes  
 La fonction d’entrée sans mise en forme extrait jusqu’à ` count` éléments et les ignore. Si ` count` est égal à **numeric_limits\<int>:: max**, toutefois, il est considéré comme arbitrairement grand. L’extraction s’arrête dès le début de la fin du fichier ou sur un élément `Ch` de sorte que la valeur de **traits_type::**[to_int_type](../standard-library/char-traits-struct.md#char_traits__to_int_type)( `Ch`) est égale à _ *Delim* (qui est également extrait). La fonction retourne **\*this**.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// basic_istream_ignore.cpp  
// compile with: /EHsc  
#include <iostream>  
int main( )   
{  
   using namespace std;  
   char chararray[10];  
   cout << "Type 'abcdef': ";  
   cin.ignore( 5, 'c' );  
   cin >> chararray;  
   cout << chararray;  
}  
```  
  
```Output  
  
abcdef  
  
```  
  
```Output  
  
abcdefdef  
```  
  
##  <a name="a-namebasicistreamoperatorgtgta--basicistreamoperatorgtgt"></a><a name="basic_istream__operator_gt__gt_"></a>  basic_istream::operator&gt;&gt;
  
Appelle une fonction sur le flux d'entrée ou lit les données mises en forme dans le flux d'entrée.  
    
```  
basic_istream& operator>>(basic_istream& (* Pfn)(basic_istream&));
basic_istream& operator>>(ios_base& (* Pfn)(ios_base&));
basic_istream& operator>>(basic_ios<Elem, Tr>& (* Pfn)(basic_ios<Elem, Tr>&));  
basic_istream& operator>>(basic_streambuf<Elem, Tr>* strbuf);
basic_istream& operator>>(bool& val);
basic_istream& operator>>(short& val);
basic_istream& operator>>(unsigned short& val);
basic_istream& operator>>(int& val);
basic_istream& operator>>(unsigned int& val);
basic_istream& operator>>(long& val);
basic_istream& operator>>(unsigned long& val);
basic_istream& operator>>(long long& val);
basic_istream& operator>>(unsigned long long& val);
basic_istream& operator>>(void *& val);
basic_istream& operator>>(float& val);
basic_istream& operator>>(double& val);
basic_istream& operator>>(long double& val);
```  
  
### <a name="parameters"></a>Paramètres  
 `Pfn`  
 Pointeur de fonction.  
  
 ` strbuf`  
 Objet de type **stream_buf**.  
  
 ` val`  
 Valeur à lire à partir du flux.  
  
### <a name="return-value"></a>Valeur de retour  
 Le flux ( **\*this**).  
  
### <a name="remarks"></a>Notes  
 L’en-tête `<istream>` définit également plusieurs opérateurs d’extraction globaux. Pour plus d’informations, consultez [operator>> (\<istream>)](../standard-library/istream-operators.md#operator_gt__gt_).  
  
 La première fonction membre garantit qu’une expression de la forme **istr** >> `ws` appelle [ws](../standard-library/istream-functions.md#ws)( **istr**), puis retourne **\*this**. Les deuxième et troisième fonctions garantissent que d’autres manipulateurs, comme [hex](../standard-library/ios-functions.md#hex), se comportent de la même façon. Les fonctions restantes constituent les fonctions d’entrée mises en forme.  
  
 La fonction :  
  
```  
basic_istream& operator>>(
    basic_streambuf<Elem, Tr>* strbuf);
```  
  
 extrait des éléments, si _ *Strbuf* n’est pas un pointeur null, et les insère dans ` strbuf`. L’extraction s’arrête à la fin du fichier. Elle s’arrête également, sans extraire l’élément en question, si une insertion échoue ou lève une exception (qui est interceptée, mais n’est pas levée à nouveau). Si la fonction n’extrait aucun élément, elle appelle [setstate](../standard-library/basic-ios-class.md#basic_ios__setstate)( **failbit**). Dans tous les cas, la fonction retourne **\*this**.  
  
 La fonction :  
  
```  
basic_istream& operator>>(bool& val);
```  
  
 extrait un champ et le convertit en valeur booléenne en appelant [use_facet](../standard-library/basic-filebuf-class.md#basic_filebuf__open) < `num_get`\< **Elem**, **InIt**>( [getloc](../standard-library/ios-base-class.md#ios_base__getloc)). [get](../standard-library/ios-base-class.md#ios_base__getloc)( **InIt**( [rdbuf](../standard-library/basic-ios-class.md#basic_ios__rdbuf)), `Init`(0), **\*this**, `getloc`, ` val`). Ici, **InIt** est défini comme [istreambuf_iterator](../standard-library/istreambuf-iterator-class.md)\< **Elem**, **Tr**>. La fonction retourne **\*this**.  
  
 Les fonctions :  
  
```  
basic_istream& operator>>(short& val);
basic_istream& operator>>(unsigned short& val);
basic_istream& operator>>(int& val);
basic_istream& operator>>(unsigned int& val);
basic_istream& operator>>(long& val);
basic_istream& operator>>(unsigned long& val); 
basic_istream& operator>>(long long& val);
basic_istream& operator>>(unsigned long long& val); 
basic_istream& operator>>(void *& val);
```  
  
 extraient chacune un champ et le convertissent en valeur numérique en appelant `use_facet`< `num_get`\< **Elem**, **InIt**>( `getloc`). [get](#basic_istream__get)( **InIt**( `rdbuf`), `Init`(0), **\*this**, `getloc`, ` val`). Ici, **InIt** est défini comme `istreambuf_iterator`\< **Elem**, **Tr**> et ` val` a le type **long***,*`unsigned long`*,* ou **void \*** selon les besoins.  
  
 Si la valeur convertie ne peut pas être représentée comme le type de ` val`, la fonction appelle [setstate](../standard-library/basic-ios-class.md#basic_ios__setstate)( **failbit**). Dans tous les cas, la fonction retourne **\*this**.  
  
 Les fonctions :  
  
```  
basic_istream& operator>>(float& val);
basic_istream& operator>>(double& val);
basic_istream& operator>>(long double& val);
```  
  
 extraient chacune un champ et le convertissent en valeur numérique en appelant `use_facet`< `num_get`\< **Elem**, **InIt**>( `getloc`). **get**( **InIt**( `rdbuf`), `Init`(0), **\*this**, `getloc`, ` val`). Ici, **InIt** est défini comme `istreambuf_iterator`\< **Elem**, **Tr**> et ` val` a le type **double** ou `long double` selon les besoins.  
  
 Si la valeur convertie ne peut pas être représentée comme le type de ` val`, la fonction appelle `setstate`( **failbit**). Dans tous les cas, elle retourne **\*this**.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// istream_basic_istream_op_is.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
  
ios_base& hex2( ios_base& ib )   
{  
   ib.unsetf( ios_base::dec );  
   ib.setf( ios_base::hex );  
   return ib;  
}  
  
basic_istream<char, char_traits<char> >& somefunc(basic_istream<char, char_traits<char> > &i)  
{  
   if ( i == cin )   
   {  
      cerr << "i is cin" << endl;  
   }  
   return i;  
}  
  
int main( )   
{  
   int i = 0;  
   cin >> somefunc;  
   cin >> i;  
   cout << i << endl;  
   cin >> hex2;  
   cin >> i;  
   cout << i << endl;  
}  
```  
  
##  <a name="a-namebasicistreamoperatoreqa--basicistreamoperator"></a><a name="basic_istream__operator_eq"></a>  basic_istream::operator=  
 Affecte le `basic_istream` du côté droit de l'opérateur à cet objet. Il s'agit d'une assignation de déplacement qui implique une référence `rvalue` qui ne laisse pas de copie.  
  
```  
basic_istream& operator=(basic_istream&& right);
```  
  
### <a name="parameters"></a>Paramètres  
 ` right`  
 Référence `rvalue` à un objet `basic_ifstream`.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne *this.  
  
### <a name="remarks"></a>Notes  
 L’opérateur membre appelle swap `( right)`.  
  
##  <a name="a-namebasicistreampeeka--basicistreampeek"></a><a name="basic_istream__peek"></a>  basic_istream::peek  
 Retourne le caractère suivant à lire.  
  
```  
int_type peek();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Caractère suivant à lire.  
  
### <a name="remarks"></a>Notes  
 La fonction d’entrée sans mise en forme extrait un élément, si possible, en retournant `rdbuf` -> [sgetc](../standard-library/basic-streambuf-class.md#basic_streambuf__sgetc). Sinon, elle retourne **traits_type::**[eof](../standard-library/char-traits-struct.md#char_traits__eof).  
  
### <a name="example"></a>Exemple  
  
```cpp  
// basic_istream_peek.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
int main( )   
{  
   char c[10], c2;  
   cout << "Type 'abcde': ";  
  
   c2 = cin.peek( );  
   cin.getline( &c[0], 9 );  
  
   cout << c2 << " " << c << endl;  
}  
```  
  
```Output  
  
abcde  
  
```  
  
```Output  
  
      abcdeType 'abcde': abcde  
a abcde  
```  
  
##  <a name="a-namebasicistreamputbacka--basicistreamputback"></a><a name="basic_istream__putback"></a>  basic_istream::putback  
 Place un caractère spécifié dans le flux.  
  
```  
basic_istream<Elem, Tr>& putback(
    char_type Ch);
```  
  
### <a name="parameters"></a>Paramètres  
 `Ch`  
 Caractère à remettre dans le flux.  
  
### <a name="return-value"></a>Valeur de retour  
 Le flux ( **\*this**).  
  
### <a name="remarks"></a>Notes  
 La [fonction d’entrée sans mise en forme](../standard-library/basic-istream-class.md) remet `Ch`, si possible, en appelant [rdbuf](../standard-library/basic-ios-class.md#basic_ios__rdbuf)`->`[sputbackc](../standard-library/basic-streambuf-class.md#basic_streambuf__sputbackc). Si rdbuf est un pointeur null ou si l’appel à `sputbackc` retourne **traits_type::**[eof](../standard-library/char-traits-struct.md#char_traits__eof), la fonction appelle [setstate](../standard-library/basic-ios-class.md#basic_ios__setstate)( **badbit**). Dans tous les cas, elle retourne **\*this**.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// basic_istream_putback.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
int main( )   
{  
   char c[10], c2, c3;  
  
   c2 = cin.get( );  
   c3 = cin.get( );  
   cin.putback( c2 );  
   cin.getline( &c[0], 9 );  
   cout << c << endl;  
}  
```  
  
```Output  
  
qwq  
```  
  
##  <a name="a-namebasicistreamreada--basicistreamread"></a><a name="basic_istream__read"></a>  basic_istream::read  
 Lit un nombre spécifié de caractères dans le flux et les stocke dans un tableau.  
  
 Cette méthode est potentiellement dangereuse, car elle suppose que l’appelant vérifie que les valeurs passées sont correctes.  
  
```  
basic_istream<Elem, Tr>& read(
    char_type* str,   
    streamsize count);
```  
  
### <a name="parameters"></a>Paramètres  
 ` str`  
 Tableau dans lequel lire les caractères.  
  
 ` count`  
 Nombre de caractères à lire.  
  
### <a name="return-value"></a>Valeur de retour  
 Le flux ( `*this`).  
  
### <a name="remarks"></a>Notes  
 La deuxième fonction d’entrée sans mise en forme extrait jusqu’à `count` éléments et les stocke dans le tableau en commençant par _ `Str`. L’extraction s’arrête dès le début de la fin du fichier, auquel cas la fonction appelle [setstate](../standard-library/basic-ios-class.md#basic_ios__setstate)( `failbit`). Dans tous les cas, elle retourne `*this`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// basic_istream_read.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
int main()  
{  
    char c[10];  
    int count = 5;  
  
    cout << "Type 'abcde': ";  
  
    // Note: cin::read is potentially unsafe, consider  
    // using cin::_Read_s instead.  
    cin.read(&c[0], count);  
    c[count] = 0;  
  
    cout << c << endl;  
}  
```  
  
```Output  
  
abcde  
  
```  
  
```Output  
  
      abcdeType 'abcde': abcde  
abcde  
```  
  
##  <a name="a-namebasicistreamreadsomea--basicistreamreadsome"></a><a name="basic_istream__readsome"></a>  basic_istream::readsome  
 Lit le nombre spécifié de valeurs de caractère.  
  
 Cette méthode est potentiellement dangereuse, car elle suppose que l’appelant vérifie que les valeurs passées sont correctes.  
  
```  
streamsize readsome(
    char_type* str,  
    streamsize count);
```  
  
### <a name="parameters"></a>Paramètres  
 `str`  
 Tableau dans lequel `readsome` stocke les caractères qu’il lit.  
  
 `count`  
 Nombre de caractères à lire.  
  
### <a name="return-value"></a>Valeur de retour  
 Nombre de caractères véritablement lus, [gcount](#basic_istream__gcount).  
  
### <a name="remarks"></a>Notes  
 Cette fonction d’entrée sans mise en forme extrait jusqu’à `count` éléments du flux d’entrée et les stocke dans le tableau `str`.  
  
 Cette fonction n’attend pas d’entrée. Elle lit toutes les données disponibles.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// basic_istream_readsome.cpp  
// compile with: /EHsc /W3  
#include <iostream>  
using namespace std;  
  
int main( )  
{  
   char c[10];  
   int count = 5;  
  
   cout << "Type 'abcdefgh': ";  
  
   // cin.read blocks until user types input.  
   // Note: cin::read is potentially unsafe, consider  
   // using cin::_Read_s instead.  
   cin.read(&c[0], 2);  
  
   // Note: cin::readsome is potentially unsafe, consider  
   // using cin::_Readsome_s instead.  
   int n = cin.readsome(&c[0], count);  // C4996  
   c[n] = 0;  
   cout << n << " characters read" << endl;  
   cout << c << endl;  
}  
```  
  
##  <a name="a-namebasicistreamseekga--basicistreamseekg"></a><a name="basic_istream__seekg"></a>  basic_istream::seekg  
 Déplace la position de lecture dans un flux.  
  
```  
basic_istream<Elem, Tr>& seekg(pos_type pos);

basic_istream<Elem, Tr>& seekg(off_type off, ios_base::seekdir way);
```  
  
### <a name="parameters"></a>Paramètres  
 `pos`  
 Position absolue à laquelle déplacer le pointeur de lecture.  
  
 `off`  
 Décalage pour déplacer le pointeur de lecture par rapport à `way`.  
  
 `way`  
 Une des énumérations [ios_base::seekdir](../standard-library/ios-base-class.md#ios_base__seekdir).  
  
### <a name="return-value"></a>Valeur de retour  
 Le flux ( **\*this**).  
  
### <a name="remarks"></a>Notes  
 La première fonction membre effectue une recherche absolue, la deuxième fonction membre effectue une recherche relative.  
  
> [!NOTE]
>  N’utilisez pas la deuxième fonction membre avec des fichiers texte, car la norme C++ ne prend pas en charge les recherches relative dans des fichiers texte.  
  
 Si [fail](../standard-library/basic-ios-class.md#basic_ios__fail) a la valeur false, la première fonction membre appelle **newpos** = [rdbuf](../standard-library/basic-ios-class.md#basic_ios__rdbuf) -> [pubseekpos](../standard-library/basic-streambuf-class.md#basic_streambuf__pubseekpos)( `pos`), pour certains objets temporaires **pos_type** **newpos**. Si **fail** a la valeur false, la deuxième fonction appelle **newpos** = **rdbuf** -> [pubseekoff](../standard-library/basic-streambuf-class.md#basic_streambuf__pubseekoff)( `off`, `way`). Dans les deux cas, si ( `off_type`) **newpos** == ( `off_type`)(-1) (l’opération de positionnement échoue), la fonction appelle **istr**. [setstate](../standard-library/basic-ios-class.md#basic_ios__setstate)( **failbit**). Les deux fonctions retournent **\*this**.  
  
 Si [fail](../standard-library/basic-ios-class.md#basic_ios__fail) a la valeur true, les fonctions membres n’effectuent aucune action.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// basic_istream_seekg.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <fstream>  
  
int main ( )   
{  
   using namespace std;  
   ifstream file;  
   char c, c1;  
  
   file.open( "basic_istream_seekg.txt" );  
   file.seekg(2);   // seek to position 2  
   file >> c;  
   cout << c << endl;  
}  
```  
  
##  <a name="a-namebasicistreamsentrya--basicistreamsentry"></a><a name="basic_istream__sentry"></a>  basic_istream::sentry  
 La classe imbriquée décrit un objet dont la déclaration structure les fonctions d’entrée avec et sans mise en forme.  
  
classe sentry {  
   publique :  
   explicit sentry( basic_istream\<Elem, Tr>& _Istr,  
   bool _Noskip = false); operator bool() const; };  
  
### <a name="remarks"></a>Notes  
 Si `_Istr``.`[good](../standard-library/basic-ios-class.md#basic_ios__good) a la valeur true, le constructeur :  
  
-   Appelle `_Istr`. [tie](../standard-library/basic-ios-class.md#basic_ios__tie) -> [flush](../standard-library/basic-ostream-class.md#basic_ostream__flush) si `_Istr`. `tie` n’est pas un pointeur null  
  
-   Appelle [ws](../standard-library/istream-functions.md#ws)( `_Istr`) si `_Istr`. [flags](../standard-library/ios-base-class.md#ios_base__flags)**&**[skipws](../standard-library/ios-functions.md#skipws) est différent de zéro  
  
 Si, après toute cette préparation, `_Istr`. **good** a la valeur false, le constructeur appelle `_Istr`. [setstate](../standard-library/basic-ios-class.md#basic_ios__setstate)( **failbit**). Dans tous les cas, le constructeur stocke la valeur retournée par `_Istr`. **good** dans **status**. Un appel ultérieur à **operator bool** fournit cette valeur stockée.  
  
##  <a name="a-namebasicistreamswapa--basicistreamswap"></a><a name="basic_istream__swap"></a>  basic_istream::swap  
 Échange le contenu de deux objets `basic_istream`.  
  
```  
void swap(basic_istream& right);
```  
  
### <a name="parameters"></a>Paramètres  
 ` right`  
 Référence lvalue à un objet `basic_istream`.  
  
### <a name="remarks"></a>Notes  
 La fonction membre appelle [basic_ios::swap](../standard-library/basic-ios-class.md#basic_ios__swap)`(`` right``)`. Elle échange également le nombre d'extractions avec le nombre d'extractions pour ` right`.  
  
##  <a name="a-namebasicistreamsynca--basicistreamsync"></a><a name="basic_istream__sync"></a>  basic_istream::sync  
 Synchronise le périphérique d’entrée associé au flux avec la mémoire tampon du flux.  
  
```  
int sync();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Si [rdbuf](../standard-library/basic-ios-class.md#basic_ios__rdbuf) est un pointeur null, la fonction retourne -1. Sinon, elle appelle `rdbuf` ->  [pubsync](../standard-library/basic-streambuf-class.md#basic_streambuf__pubsync). Si le résultat est -1, la fonction appelle [setstate](../standard-library/basic-ios-class.md#basic_ios__setstate)( **badbit**) et retourne -1. Sinon, la fonction retourne zéro.  
  
##  <a name="a-namebasicistreamtellga--basicistreamtellg"></a><a name="basic_istream__tellg"></a>  basic_istream::tellg  
 Indique la position de lecture actuelle dans le flux.  
  
```  
pos_type tellg();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Position actuelle dans le flux.  
  
### <a name="remarks"></a>Notes  
 Si [fail](../standard-library/basic-ios-class.md#basic_ios__fail) a la valeur false, la fonction membre retourne [rdbuf](../standard-library/basic-ios-class.md#basic_ios__rdbuf) -> [pubseekoff](../standard-library/basic-streambuf-class.md#basic_streambuf__pubseekoff)(0, `cur`, **in**). Sinon, elle retourne `pos_type`(-1).  
  
### <a name="example"></a>Exemple  
  
```cpp  
// basic_istream_tellg.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <fstream>  
  
int main()  
{  
    using namespace std;  
    ifstream file;  
    char c;  
    streamoff i;  
  
    file.open("basic_istream_tellg.txt");  
    i = file.tellg();  
    file >> c;  
    cout << c << " " << i << endl;  
  
    i = file.tellg();  
    file >> c;  
    cout << c << " " << i << endl;  
}  
```  
  
##  <a name="a-namebasicistreamungeta--basicistreamunget"></a><a name="basic_istream__unget"></a>  basic_istream::unget  
 Replace le dernier caractère lu dans le flux.  
  
```  
basic_istream<Elem, Tr>& unget();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le flux ( **\*this**).  
  
### <a name="remarks"></a>Notes  
 La [fonction d’entrée sans mise en forme](../standard-library/basic-istream-class.md) remet l’élément précédent dans le flux, si possible, en appelant `rdbuf` -> [sungetc](../standard-library/basic-streambuf-class.md#basic_streambuf__sungetc). Si [rdbuf](../standard-library/basic-ios-class.md#basic_ios__rdbuf) est un pointeur null ou si l’appel à `sungetc` retourne **traits_type::**[eof](../standard-library/basic-ios-class.md#basic_ios__eof), la fonction appelle [setstate](../standard-library/basic-ios-class.md#basic_ios__setstate)( **badbit**). Dans tous les cas, elle retourne **\*this**.  
  
 Pour plus d’informations sur l’échec possible de `unget`, consultez [basic_streambuf::sungetc](../standard-library/basic-streambuf-class.md#basic_streambuf__sungetc).  
  
### <a name="example"></a>Exemple  
  
```cpp  
// basic_istream_unget.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
int main( )   
{  
   char c[10], c2;  
  
   cout << "Type 'abc': ";  
   c2 = cin.get( );  
   cin.unget( );  
   cin.getline( &c[0], 9 );  
   cout << c << endl;  
}  
```  
  
```Output  
  
abc  
  
```  
  
```Output  
  
      abcType 'abc': abc  
abc  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream, programmation](../standard-library/iostream-programming.md)   
 [iostreams, conventions](../standard-library/iostreams-conventions.md)



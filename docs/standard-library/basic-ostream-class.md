---
title: basic_ostream, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std::basic_ostream
- std.basic_ostream
- ostream/std::basic_ostream
- basic_ostream
dev_langs:
- C++
helpviewer_keywords:
- basic_ostream class
ms.assetid: 5baadc65-b662-4fab-8c9f-94457c58cda1
caps.latest.revision: 24
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.openlocfilehash: 73cde54e382bb04b82739239bd0f07142c5b3321
ms.lasthandoff: 02/24/2017

---
# <a name="basicostream-class"></a>basic_ostream, classe
Cette classe de modèle décrit un objet qui contrôle l’insertion d’éléments et d’objets codés dans une mémoire tampon de flux avec des éléments de type **Elem**, également appelé [char_type](../standard-library/basic-ios-class.md#basic_ios__char_type), dont les caractéristiques sont déterminées par la classe **Tr**, également appelée [traits_type](../standard-library/basic-ios-class.md#basic_ios__traits_type).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <class Elem, class Tr = char_traits<Elem>>  
class basic_ostream : virtual public basic_ios<Elem, Tr>  
```  
  
#### <a name="parameters"></a>Paramètres  
 `Elem`  
 `char_type`  
  
 `Tr`  
 `traits_type` du caractère.  
  
## <a name="remarks"></a>Notes  
 La plupart des fonctions membres qui surchargent [operator<<](#basic_ostream__operator_lt__lt_) sont des fonctions de sortie mises en forme. Elles suivent le modèle :  
  
```  
iostate state = goodbit;  
const sentry ok(*this);

if (ok)  
 {try  
 {<convert and insert elements  
    accumulate flags in state> }  
    catch (...)  
 {try  
 {setstate(badbit);

}  
    catch (...)  
 {}  
    if ((exceptions()& badbit) != 0)  
    throw; }}  
width(0);
// Except for operator<<(Elem)  
setstate(state);

return (*this);
```  
  
 Deux autres fonctions membres sont des fonctions de sortie non mises en forme. Elles suivent le modèle :  
  
```  
iostate state = goodbit;  
const sentry ok(*this);

if (!ok)  
    state |= badbit;  
else  
 {try  
 {<obtain and insert elements  
    accumulate flags in state> }  
    catch (...)  
 {try  
 {setstate(badbit);

}  
    catch (...)  
 {}  
    if ((exceptions()& badbit) != 0)  
    throw; }}  
setstate(state);

return (*this);
```  
  
 Ces deux groupes de fonctions appellent [setstate](../standard-library/basic-ios-class.md#basic_ios__setstate)**(badbit)** si elles rencontrent un échec lors de l’insertion d’éléments.  
  
 Un objet de classe basic_istream \< **Elem**, **Tr**> stocke seulement un objet de base public virtuel de classe [basic_ios](../standard-library/basic-ios-class.md)**\<Elem**, **Tr>**.  
  
## <a name="example"></a>Exemple  
 Pour en savoir plus sur les flux de sortie, consultez l’exemple relatif à [basic_ofstream, classe](../standard-library/basic-ofstream-class.md).  
  
### <a name="constructors"></a>Constructeurs  
  
|||  
|-|-|  
|[basic_ostream](#basic_ostream__basic_ostream)|Construit un objet `basic_ostream`.|  
  
### <a name="member-functions"></a>Fonctions membres  
  
|||  
|-|-|  
|[flush](#basic_ostream__flush)|Vide la mémoire tampon.|  
|[put](#basic_ostream__put)|Place un caractère dans un flux.|  
|[seekp](#basic_ostream__seekp)|Réinitialise la position dans le flux de sortie.|  
|[sentry](#basic_ostream__sentry)|La classe imbriquée décrit un objet dont la déclaration structure les fonctions de sortie mise en forme et les fonctions de sortie non mise en forme.|  
|[swap](#basic_ostream__operator_eq)|Échange les valeurs de cet objet `basic_ostream` avec celles de l'objet `basic_ostream` fourni.|  
|[tellp](#basic_ostream__tellp)|Indique la position dans le flux de sortie.|  
|[write](#basic_ostream__write)|Place des caractères dans un flux.|  
  
### <a name="operators"></a>Opérateurs  
  
|||  
|-|-|  
|[operator=](#basic_ostream_operator_eq)|Affecte la valeur du paramètre d'objet `basic_ostream` fourni à cet objet.|  
|[operator<<](#basic_ostream_operator_lt_lt_)|Écrit dans le flux.|  

## <a name="requirements"></a>Spécifications  
 **En-tête :** \<ostream>  
  
 **Espace de noms :** std  
  
##  <a name="a-namebasicostreambasicostreama--basicostreambasicostream"></a><a name="basic_ostream__basic_ostream"></a>  basic_ostream::basic_ostream  
 Construit un objet `basic_ostream`.  
  
```  
explicit basic_ostream(
    basic_streambuf<Elem, Tr>* strbuf,  
    bool _Isstd = false);

basic_ostream(basic_ostream&& right);
```  
  
### <a name="parameters"></a>Paramètres  
 ` strbuf`  
 Objet de type [basic_streambuf](../standard-library/basic-streambuf-class.md).  
  
 `_Isstd`  
 `true` s’il s’agit d’un flux standard ; sinon, `false`.  
  
 ` right`  
 Référence rvalue à un objet de type `basic_ostream`.  
  
### <a name="remarks"></a>Notes  
 Le premier constructeur initialise la classe de base en appelant [init](../standard-library/basic-ios-class.md#basic_ios__init)(` strbuf`). Le deuxième constructeur initialise la classe de base en appelant [basic_ios::move](../standard-library/basic-ios-class.md#basic_ios__move)`(`` right``)`.  
  
### <a name="example"></a>Exemple  
  Pour en savoir plus sur les flux de sortie, consultez l’exemple relatif à [basic_ofstream::basic_ofstream](../standard-library/basic-ofstream-class.md#basic_ofstream__basic_ofstream).  
  
##  <a name="a-namebasicostreamflusha--basicostreamflush"></a><a name="basic_ostream__flush"></a>  basic_ostream::flush  
 Vide la mémoire tampon.  
  
```  
basic_ostream<Elem, Tr>& flush();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Référence à l’objet basic_ostream.  
  
### <a name="remarks"></a>Notes  
 Si [rdbuf](../standard-library/basic-ios-class.md#basic_ios__rdbuf) n’est pas un pointeur null, la fonction membre appelle **rdbuf->**[pubsync](../standard-library/basic-streambuf-class.md#basic_streambuf__pubsync). Si le résultat est -1, la fonction appelle [setstate](../standard-library/basic-ios-class.md#basic_ios__setstate)(**badbit**). Elle retourne ensuite **\*this**.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// basic_ostream_flush.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   cout << "test";  
   cout.flush();  
}  
```  
  
```Output  
test  
```  
  
##  <a name="a-namebasicostreamoperatorltlta--basicostreamoperatorltlt"></a><a name="basic_ostream_operator_lt_lt_"></a>  basic_ostream::operator&lt;&lt;  
 Écrit dans le flux.  
  
```  
basic_ostream<Elem, Tr>& operator<<(
    basic_ostream<Elem, Tr>& (* Pfn)(basic_ostream<Elem, Tr>&));

basic_ostream<Elem, Tr>& operator<<(
    ios_base& (* Pfn)(ios_base&));

basic_ostream<Elem, Tr>& operator<<(
    basic_ios<Elem, Tr>& (* Pfn)(basic_ios<Elem, Tr>&));

basic_ostream<Elem, Tr>& operator<<(basic_streambuf<Elem, Tr>* strbuf);
basic_ostream<Elem, Tr>& operator<<(bool val);
basic_ostream<Elem, Tr>& operator<<(short val);
basic_ostream<Elem, Tr>& operator<<(unsigned short val);
basic_ostream<Elem, Tr>& operator<<(int __w64  val);
basic_ostream<Elem, Tr>& operator<<(unsigned int __w64  val);
basic_ostream<Elem, Tr>& operator<<(long val);
basic_ostream<Elem, Tr>& operator<<(unsigned long __w64  val);
basic_ostream<Elem, Tr>& operator<<(long long val);
basic_ostream<Elem, Tr>& operator<<(unsigned long long val);
basic_ostream<Elem, Tr>& operator<<(float val);
basic_ostream<Elem, Tr>& operator<<(double val);
basic_ostream<Elem, Tr>& operator<<(long double val);
basic_ostream<Elem, Tr>& operator<<(const void* val);
```  
  
### <a name="parameters"></a>Paramètres  
 `Pfn`  
 Pointeur de fonction.  
  
 ` strbuf`  
 Pointeur vers un objet **stream_buf**.  
  
 ` val`  
 Élément à écrire dans le flux.  
  
### <a name="return-value"></a>Valeur de retour  
 Référence à l’objet basic_ostream.  
  
### <a name="remarks"></a>Notes  
 L’en-tête `<ostream>` définit également plusieurs opérateurs d’insertion globaux. Pour plus d’informations, consultez [operator<<\<ostream>](../standard-library/ostream-operators.md#operator_lt__lt_).  
  
 La première fonction membre garantit qu’une expression de la forme **ostr << endl** appelle [endl](../standard-library/ostream-functions.md#endl)**(ostr)**, puis retourne **\*this**. Les deuxième et troisième fonctions garantissent que d’autres manipulateurs, comme [hex](../standard-library/ios-functions.md#hex), se comportent de la même façon. Les fonctions restantes sont toutes les fonctions de sortie mises en forme.  
  
 La fonction  
  
```  
basic_ostream<Elem, Tr>& operator<<(basic_streambuf<Elem, Tr>* strbuf);
```  
  
 extrait des éléments de ` strbuf`, si ` strbuf` n’est pas un pointeur null, et les insère. L’extraction s’arrête à la fin du fichier ou si une extraction lève une exception (qui est à nouveau levée). Elle s’arrête également, sans extraire l’élément en question, si une insertion échoue. Si la fonction n’insère aucun élément ou si une extraction lève une exception, la fonction appelle [setstate](../standard-library/basic-ios-class.md#basic_ios__setstate)(**failbit**). Dans tous les cas, la fonction retourne **\*this**.  
  
 La fonction  
  
```  
basic_ostream<Elem, Tr>& operator<<(bool val);
```  
  
 convertit _`Val` en champ booléen et l’insère en appelant [use_facet](../standard-library/basic-filebuf-class.md#basic_filebuf__open)**<num_put\<Elem, Outlt>**`(`[getloc](../standard-library/ios-base-class.md#ios_base__getloc)). [put](#basic_ostream__put)(**OutIt**([rdbuf](../standard-library/basic-ios-class.md#basic_ios__rdbuf)), **\*this**, `getloc`, **val**). Ici, **Outlt** est défini comme [ostreambuf_iterator](../standard-library/ostreambuf-iterator-class.md)**\<Elem, Tr>**. La fonction retourne **\*this**.  
  
 Les fonctions  
  
```  
basic_ostream<Elem, Tr>& operator<<(short val);
basic_ostream<Elem, Tr>& operator<<(unsigned short val);
basic_ostream<Elem, Tr>& operator<<(int val);
basic_ostream<Elem, Tr>& operator<<(unsigned int __w64  val);
basic_ostream<Elem, Tr>& operator<<(long val);
basic_ostream<Elem, Tr>& operator<<(unsigned long val);
basic_ostream<Elem, Tr>& operator<<(long long val);
basic_ostream<Elem, Tr>& operator<<(unsigned long long val);
basic_ostream<Elem, Tr>& operator<<(const void* val);
```  
  
 convertissent chacune ` val` en champ numérique et l’insèrent en appelant **use_facet<num_put\<Elem, Outlt>**(`getloc`). **put**(**OutIt**(`rdbuf`), **\*this**, `getloc`, **val**). Ici, **Outlt** est défini comme **ostreambuf_iterator\<Elem, Tr>**. La fonction retourne **\*this**.  
  
 Les fonctions  
  
```  
basic_ostream<Elem, Tr>& operator<<(float val);
basic_ostream<Elem, Tr>& operator<<(double val);
basic_ostream<Elem, Tr>& operator<<(long double val);
```  
  
 convertissent chacune `val` en champ numérique et l’insèrent en appelant **use_facet<num_put\<Elem, Outlt>**(`getloc`)**. put**(**Outlt**(`rdbuf`), **\*this**, `getloc`, **val**). Ici, **Outlt** est défini comme **ostreambuf_iterator\<Elem, Tr>**. La fonction retourne **\*this**.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// basic_ostream_op_write.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <string.h>  
  
using namespace std;  
  
ios_base& hex2( ios_base& ib )  
{  
   ib.unsetf( ios_base::dec );  
   ib.setf( ios_base::hex );  
   return ib;  
}  
  
basic_ostream<char, char_traits<char> >& somefunc(basic_ostream<char, char_traits<char> > &i)
{
    if (i == cout)
    {
        i << "i is cout" << endl;
    }
    return i;
}

class CTxtStreambuf : public basic_streambuf< char, char_traits< char > >
{
public:
    CTxtStreambuf(char *_pszText)
    {
        pszText = _pszText;
        setg(pszText, pszText, pszText + strlen(pszText));
    };
    char *pszText;
};

int main()
{
    cout << somefunc;
    cout << 21 << endl;

    hex2(cout);
    cout << 21 << endl;

    CTxtStreambuf f("text in streambuf");
    cout << &f << endl;
}
```  
  
##  <a name="a-namebasicostreamoperatoreqa--basicostreamoperator"></a><a name="basic_ostream__operator_eq"></a>  basic_ostream::operator=  
 Attribue la valeur du paramètre d’objet `basic_ostream` fourni à cet objet.  
  
```  
basic_ostream& operator=(basic_ostream&& right);
```  
  
### <a name="parameters"></a>Paramètres  
 ` right`  
 Référence `rvalue` à un objet `basic_ostream`.  
  
### <a name="remarks"></a>Notes  
 L’opérateur membre appelle swap `(`` right``)`.  
  
##  <a name="a-namebasicostreamputa--basicostreamput"></a><a name="basic_ostream__put"></a>  basic_ostream::put  
 Place un caractère dans un flux.  
  
```  
basic_ostream<Elem, Tr>& put(char_type _Ch);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Ch`  
 Un caractère.  
  
### <a name="return-value"></a>Valeur de retour  
 Référence à l’objet basic_ostream.  
  
### <a name="remarks"></a>Notes  
 La fonction de sortie sans mise en forme insère l’élément `_Ch`. Elle retourne ensuite **\*this**.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// basic_ostream_put.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   cout.put( 'v' );  
   cout << endl;  
   wcout.put( L'l' );  
}  
```  
  
```Output  
v  
l  
```  
  
##  <a name="a-namebasicostreamseekpa--basicostreamseekp"></a><a name="basic_ostream__seekp"></a>  basic_ostream::seekp  
 Réinitialise la position dans le flux de sortie.  
  
```  
basic_ostream<Elem, Tr>& seekp(pos_type _Pos);

basic_ostream<Elem, Tr>& seekp(off_type _Off, ios_base::seekdir _Way);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Pos`  
 Position dans le flux.  
  
 `_Off`  
 Décalage par rapport à `_Way`.  
  
 `_Way`  
 Une des énumérations [ios_base::seekdir](../standard-library/ios-base-class.md#ios_base__seekdir).  
  
### <a name="return-value"></a>Valeur de retour  
 Référence à l’objet basic_ostream.  
  
### <a name="remarks"></a>Notes  
 Si [fail](../standard-library/basic-ios-class.md#basic_ios__fail) est **false**, la première fonction membre appelle **newpos =** [rdbuf](../standard-library/basic-ios-class.md#basic_ios__rdbuf)**->** [pubseekpos](../standard-library/basic-streambuf-class.md#basic_streambuf__pubseekpos)(_*Pos*), pour certains objets temporaires `pos_type` **newpos**. Si **fail** a la valeur false, la deuxième fonction appelle **newpos = rdbuf->** [pubseekoff](../standard-library/basic-streambuf-class.md#basic_streambuf__pubseekoff)(*_Off, _Way*). Dans les deux cas, si (`off_type`)**newpos ==** (`off_type`)(-1) (l’opération de positionnement échoue), la fonction appelle **istr.**[setstate](../standard-library/basic-ios-class.md#basic_ios__setstate)(**failbit**). Les deux fonctions retournent **\*this**.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// basic_ostream_seekp.cpp  
// compile with: /EHsc  
#include <fstream>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
    ofstream x("basic_ostream_seekp.txt");  
    streamoff i = x.tellp();  
    cout << i << endl;  
    x << "testing";  
    i = x.tellp();  
    cout << i << endl;  
    x.seekp(2);   // Put char in third char position in file  
    x << " ";  
  
    x.seekp(2, ios::end);   // Put char two after end of file  
    x << "z";  
}  
```  
  
```Output  
0  
7  
```  
  
##  <a name="a-namebasicostreamsentrya--basicostreamsentry"></a><a name="basic_ostream__sentry"></a>  basic_ostream::sentry  
 La classe imbriquée décrit un objet dont la déclaration structure les fonctions de sortie mise en forme et les fonctions de sortie non mise en forme.  
  
classe sentry {  
   publique :  
   explicit sentry(basic_ostream\<Elem, Tr>& _Ostr); operator bool() const; ~sentry(); };  
  
### <a name="remarks"></a>Notes  
 La classe imbriquée décrit un objet dont la déclaration structure les fonctions de sortie mise en forme et les fonctions de sortie non mise en forme. Si **ostr.**[good](../standard-library/basic-ios-class.md#basic_ios__good) est **true** et **ostr.**[tie](../standard-library/basic-ios-class.md#basic_ios__tie) n’est pas un pointeur null, le constructeur appelle **ostr.tie->**[flush](#basic_ostream__flush). Le constructeur stocke ensuite la valeur retournée par **ostr.good** dans **status**. Un appel ultérieur à **operator bool** fournit cette valeur stockée.  
  
 Si `uncaught_exception` retourne **false** et [flags](../standard-library/ios-base-class.md#ios_base__flags) **&** [unitbuf](../standard-library/ios-functions.md#unitbuf) est différent de zéro, le destructeur appelle [flush](#basic_ostream__flush).  
  
##  <a name="a-namebasicostreamswapa--basicostreamswap"></a><a name="basic_ostream__swap"></a>  basic_ostream::swap  
 Échange les valeurs de cet objet `basic_ostream` avec celles du `basic_ostream` fourni.  
  
```  
void swap(basic_ostream& right);
```  
  
### <a name="parameters"></a>Paramètres  
 ` right`  
 Référence à un objet `basic_ostream`.  
  
### <a name="remarks"></a>Notes  
 La fonction membre appelle [basic_ios::swap](../standard-library/basic-ios-class.md#basic_ios__swap)`(`` right``)` pour échanger le contenu de cet objet avec celui de ` right`.  
  
##  <a name="a-namebasicostreamtellpa--basicostreamtellp"></a><a name="basic_ostream__tellp"></a>  basic_ostream::tellp  
 Signale la position dans le flux de sortie.  
  
```  
pos_type tellp();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Position dans le flux de sortie.  
  
### <a name="remarks"></a>Notes  
 Si [fail](../standard-library/basic-ios-class.md#basic_ios__fail) est **false**, la fonction membre retourne [rdbuf](../standard-library/basic-ios-class.md#basic_ios__rdbuf)**->** [pubseekoff](../standard-library/basic-streambuf-class.md#basic_streambuf__pubseekoff)(0, `cur`, **in**). Sinon, elle retourne `pos_type`(-1).  
  
### <a name="example"></a>Exemple  
  Consultez [seekp](#basic_ostream__seekp) pour obtenir un exemple d’utilisation de `tellp`.  
  
##  <a name="a-namebasicostreamwritea--basicostreamwrite"></a><a name="basic_ostream__write"></a>  basic_ostream::write  
 Place des caractères dans un flux.  
  
```  
basic_ostream<Elem, Tr>& write(const char_type* str, streamsize count);
```  
  
### <a name="parameters"></a>Paramètres  
 ` count`  
 Nombre de caractères à placer dans le flux.  
  
 ` str`  
 Caractères à placer dans le flux.  
  
### <a name="return-value"></a>Valeur de retour  
 Référence à l’objet basic_ostream.  
  
### <a name="remarks"></a>Notes  
 La [fonction de sortie sans mise en forme](../standard-library/basic-ostream-class.md) insère la séquence d’éléments ` count` en commençant par ` str`.  
  
### <a name="example"></a>Exemple  
  Consultez [streamsize](../standard-library/ios-typedefs.md#streamsize) pour obtenir un exemple d’utilisation de `write`.  
  
## <a name="see-also"></a>Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream, programmation](../standard-library/iostream-programming.md)   
 [iostreams, conventions](../standard-library/iostreams-conventions.md)



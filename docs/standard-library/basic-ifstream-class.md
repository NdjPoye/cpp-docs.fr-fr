---
title: basic_ifstream, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- basic_ifstream
- fstream/std::basic_ifstream
- std::basic_ifstream
- std.basic_ifstream
dev_langs:
- C++
helpviewer_keywords:
- basic_ifstream class
ms.assetid: 366cd9a7-efc4-4b7f-ba10-c8271e47ffcf
caps.latest.revision: 23
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: afbd83cc6197e274c2921810b8b167a5d7f8b8a6
ms.lasthandoff: 02/24/2017

---
# <a name="basicifstream-class"></a>basic_ifstream, classe
Décrit un objet qui contrôle l’extraction d’éléments et d’objets codés à partir d’une mémoire tampon de flux de classe [basic_filebuf](../standard-library/basic-filebuf-class.md)< `Elem`, `Tr`>, avec des éléments de type `Elem`, dont les caractéristiques sont déterminées par la classe `Tr`.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <class Elem, class Tr = char_traits<Elem>>  
class basic_ifstream : public basic_istream<Elem, Tr>  
```  
  
#### <a name="parameters"></a>Paramètres  
 `Elem`  
 Élément de base de la mémoire tampon de fichier.  
  
 `Tr`  
 Caractéristiques de l’élément de base de la mémoire tampon de fichier (généralement `char_traits`< `Elem`>).  
  
## <a name="remarks"></a>Notes  
 L’objet stocke un objet de classe `basic_filebuf`< `Elem`, `Tr`>.  
  
## <a name="example"></a>Exemple  
 L'exemple suivant montre comment lire le texte d'un fichier.  
  
```  
// basic_ifstream_class.cpp  
// compile with: /EHsc  
  
#include <fstream>  
#include <iostream>  
  
using namespace std;  
  
int main(int argc, char **argv)  
{  
    ifstream ifs("basic_ifstream_class.txt");  
    if (!ifs.bad())  
    {  
        // Dump the contents of the file to cout.  
        cout << ifs.rdbuf();  
        ifs.close();  
    }  
}  
```  
  
## <a name="input-basicifstreamclasstxt"></a>Entrée : basic_ifstream_class.txt  
  
```  
This is the contents of basic_ifstream_class.txt.  
```  
  
## <a name="output"></a>Sortie  
  
```  
This is the contents of basic_ifstream_class.txt.  
```  
  
### <a name="constructors"></a>Constructeurs  
  
|||  
|-|-|  
|[basic_ifstream](#basic_ifstream__basic_ifstream)|Initialise une nouvelle instance d'un objet `basic_ifstream`.|  
  
### <a name="member-functions"></a>Fonctions membres  
  
|||  
|-|-|  
|[close](#basic_ifstream__close)|Ferme un fichier.|  
|[is_open](#basic_ifstream__is_open)|Détermine si un fichier est ouvert.|  
|[open](#basic_ifstream__open)|Ouvre un fichier.|  
|[rdbuf](#basic_ifstream__rdbuf)|Retourne l'adresse de la mémoire tampon de flux stockée.|  
|[swap](#basic_ifstream__swap)|Échange le contenu de ce `basic_ifstream` avec le contenu du `basic_ifstream` fourni.|  
  
### <a name="operators"></a>Opérateurs  
  
|||  
|-|-|  
|[operator=](#basic_ifstream__operator_eq)|Assigne le contenu de cet objet de flux. Il s'agit d'une assignation de déplacement impliquant une `rvalue` qui ne laisse pas de copie.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<fstream>  
  
 **Espace de noms :** std  
  
##  <a name="a-namebasicifstreambasicifstreama--basicifstreambasicifstream"></a><a name="basic_ifstream__basic_ifstream"></a>  basic_ifstream::basic_ifstream  
 Construit un objet de type `basic_ifstream`.  
  
```  
basic_ifstream();

explicit basic_ifstream(
    const char* _Filename,  
    ios_base::openmode _Mode = ios_base::in,  
    int _Prot = (int)ios_base::_Openprot);

explicit basic_ifstream(
    const wchar_t* _Filename,  
    ios_base::openmode _Mode = ios_base::in,  
    int _Prot = (int)ios_base::_Openprot);

basic_ifstream(basic_ifstream&& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Filename`  
 Nom du fichier à ouvrir.  
  
 `_Mode`  
 Une des énumérations dans [ios_base::openmode](../standard-library/ios-base-class.md#ios_base__openmode).  
  
 `_Prot`  
 Protection d’ouverture de fichier par défaut, équivalente au paramètre `shflag` dans [_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md).  
  
### <a name="remarks"></a>Notes  
 Le premier constructeur initialise la classe de base en appelant [basic_istream](../standard-library/basic-istream-class.md)( `sb`), où `sb` est l’objet stocké de classe [basic_filebuf](../standard-library/basic-filebuf-class.md)< `Elem`, `Tr`>. Il initialise également `sb` en appelant `basic_filebuf`< `Elem`, `Tr`>.  
  
 Les deuxième et troisième constructeurs initialisent la classe de base en appelant `basic_istream`( `sb`). Ils initialisent également `sb` en appelant [basic_filebuf](../standard-library/basic-filebuf-class.md#basic_filebuf__basic_filebuf)< `Elem`, `Tr`>, puis `sb`. [open](../standard-library/basic-filebuf-class.md#basic_filebuf__open)( `_Filename`, `_Mode` &#124; `ios_base::in`). Si cette dernière fonction retourne un pointeur null, le constructeur appelle **setstate**( `failbit`).  
  
 Le quatrième constructeur initialise l’objet avec le contenu de `right`, traité comme une référence rvalue.  
  
### <a name="example"></a>Exemple  
  L'exemple suivant montre comment lire le texte d'un fichier. Pour créer le fichier, consultez l’exemple de [basic_ofstream::basic_ofstream](../standard-library/basic-ofstream-class.md#basic_ofstream__basic_ofstream).  
  
```  
// basic_ifstream_ctor.cpp  
// compile with: /EHsc  
  
#include <fstream>  
#include <iostream>  
  
using namespace std;  
  
int main(int argc, char **argv)  
{  
    ifstream ifs("basic_ifstream_ctor.txt");  
    if (!ifs.bad())  
    {  
        // Dump the contents of the file to cout.  
        cout << ifs.rdbuf();  
        ifs.close();  
    }  
}  
```  
  
##  <a name="a-namebasicifstreamclosea--basicifstreamclose"></a><a name="basic_ifstream__close"></a>  basic_ifstream::close  
 Ferme un fichier.  
  
```  
void close();
```  
  
### <a name="remarks"></a>Notes  
 La fonction membre appelle [rdbuf](#basic_ifstream__rdbuf) **->** [close](../standard-library/basic-filebuf-class.md#basic_filebuf__close).  
  
### <a name="example"></a>Exemple  
  Consultez [basic_filebuf::close](../standard-library/basic-filebuf-class.md#basic_filebuf__close) pour obtenir un exemple qui utilise **close**.  
  
##  <a name="a-namebasicifstreamisopena--basicifstreamisopen"></a><a name="basic_ifstream__is_open"></a>  basic_ifstream::is_open  
 Détermine si un fichier est ouvert.  
  
```  
bool is_open() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si le fichier est ouvert, **false** dans le cas contraire.  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne [rdbuf](#basic_ifstream__rdbuf) **->** [is_open](../standard-library/basic-filebuf-class.md#basic_filebuf__is_open).  
  
### <a name="example"></a>Exemple  
  Consultez [basic_filebuf::is_open](../standard-library/basic-filebuf-class.md#basic_filebuf__is_open) pour obtenir un exemple qui utilise `is_open`.  
  
##  <a name="a-namebasicifstreamopena--basicifstreamopen"></a><a name="basic_ifstream__open"></a>  basic_ifstream::open  
 Ouvre un fichier.  
  
```  
void open(
    const char* _Filename,  
    ios_base::openmode _Mode = ios_base::in,  
    int _Prot = (int)ios_base::_Openprot);

void open(
    const char* _Filename,  
    ios_base::openmode _Mode);

void open(
    const wchar_t* _Filename,  
    ios_base::openmode _Mode = ios_base::in,  
    int _Prot = (int)ios_base::_Openprot);

void open(
    const wchar_t* _Filename,  
    ios_base::openmode _Mode);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Filename`  
 Nom du fichier à ouvrir.  
  
 `_Mode`  
 Une des énumérations dans [ios_base::openmode](../standard-library/ios-base-class.md#ios_base__openmode).  
  
 `_Prot`  
 Protection d’ouverture de fichier par défaut, équivalente au paramètre `shflag` dans [_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md).  
  
### <a name="remarks"></a>Notes  
 La fonction membre appelle [rdbuf](#basic_ifstream__rdbuf) **->** [open](../standard-library/basic-filebuf-class.md#basic_filebuf__open)(_ *Filename*, `_Mode` &#124; **ios_base::in**). Si open échoue, la fonction appelle [setstate](../standard-library/basic-ios-class.md#basic_ios__setstate)( **failbit**) qui peut lever une exception ios_base::failure.  
  
### <a name="example"></a>Exemple  
  Consultez [basic_filebuf::open](../standard-library/basic-filebuf-class.md#basic_filebuf__open) pour obtenir un exemple qui utilise **open**.  
  
##  <a name="a-namebasicifstreamoperatoreqa--basicifstreamoperator"></a><a name="basic_ifstream__operator_eq"></a>  basic_ifstream::operator=  
 Assigne le contenu de cet objet de flux. Il s'agit d'une assignation de déplacement qui implique une rvalue qui ne laisse pas de copie.  
  
```  
basic_ifstream& operator=(basic_ifstream&& right);
```  
  
### <a name="parameters"></a>Paramètres  
 ` right`  
 Référence rvalue à un objet `basic_ifstream`.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne `*this`.  
  
### <a name="remarks"></a>Notes  
 L'opérateur membre remplace le contenu de l'objet à l'aide du contenu de ` right`, traité comme une référence rvalue. Pour plus d’informations, consultez [Lvalues et Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md).  
  
##  <a name="a-namebasicifstreamrdbufa--basicifstreamrdbuf"></a><a name="basic_ifstream__rdbuf"></a>  basic_ifstream::rdbuf  
 Retourne l'adresse de la mémoire tampon de flux stockée.  
  
```  
basic_filebuf<Elem, Tr> *rdbuf() const 
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers un objet [basic_filebuf](../standard-library/basic-filebuf-class.md) qui représente la mémoire tampon de flux stockée.  
  
### <a name="example"></a>Exemple  
  Consultez [basic_filebuf::close](../standard-library/basic-filebuf-class.md#basic_filebuf__close) pour obtenir un exemple qui utilise `rdbuf`.  
  
##  <a name="a-namebasicifstreamswapa--basicifstreamswap"></a><a name="basic_ifstream__swap"></a>  basic_ifstream::swap  
 Échange le contenu de deux objets `basic_ifstream`.  
  
```  
void swap(basic_ifstream& right);
```  
  
### <a name="parameters"></a>Paramètres  
 ` right`  
 Référence à une autre mémoire tampon de flux.  
  
### <a name="remarks"></a>Notes  
 La fonction membre échange le contenu de cet objet avec celui de ` right`.  
  
## <a name="see-also"></a>Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream, programmation](../standard-library/iostream-programming.md)   
 [iostreams, conventions](../standard-library/iostreams-conventions.md)




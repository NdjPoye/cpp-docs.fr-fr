---
title: basic_fstream, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- basic_fstream
- fstream/std::basic_fstream
- fstream/std::basic_fstream::close
- fstream/std::basic_fstream::is_open
- fstream/std::basic_fstream::open
- fstream/std::basic_fstream::rdbuf
- fstream/std::basic_fstream::swap
dev_langs:
- C++
helpviewer_keywords:
- basic_fstream class
ms.assetid: 8473817e-42a4-430b-82b8-b476c86bcf8a
caps.latest.revision: 24
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: f9d52128703d021ba3a880ff899ca71b144e89ec
ms.contentlocale: fr-fr
ms.lasthandoff: 04/29/2017

---
# <a name="basicfstream-class"></a>basic_fstream, classe
Décrit un objet qui contrôle l’insertion et l’extraction d’éléments et d’objets codés à l’aide d’une mémoire tampon de flux de classe [basic_filebuf](../standard-library/basic-filebuf-class.md)< `Elem`, `Tr`>, avec des éléments de type `Elem`, dont les caractéristiques sont déterminées par la classe `Tr`.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <class Elem, class Tr = char_traits<Elem>>  
class basic_fstream : public basic_iostream<Elem, Tr>  
```  
  
#### <a name="parameters"></a>Paramètres  
 `Elem`  
 Élément de base de la mémoire tampon de fichier.  
  
 `Tr`  
 Caractéristiques de l’élément de base de la mémoire tampon de fichier (généralement `char_traits`< `Elem`>).  
  
## <a name="remarks"></a>Notes  
 L’objet stocke un objet de classe `basic_filebuf`< `Elem`, `Tr`>.  
  
> [!NOTE]
>  Les pointeurs get et put d’un objet fstream ne sont **PAS** indépendants l’un de l’autre. Si le pointeur get bouge, le pointeur put bouge aussi.  
  
## <a name="example"></a>Exemple  
 L'exemple suivant montre comment créer un objet `basic_fstream` qui peut être lu et écrit.  
  
```  
// basic_fstream_class.cpp  
// compile with: /EHsc  
  
#include <fstream>  
#include <iostream>  
  
using namespace std;  
  
int main(int argc, char **argv)  
{  
    fstream fs("fstream.txt", ios::in | ios::out | ios::trunc);  
    if (!fs.bad())  
    {  
        // Write to the file.  
        fs << "Writing to a basic_fstream object..." << endl;  
        fs.close();  
  
        // Dump the contents of the file to cout.  
        fs.open("fstream.txt", ios::in);  
        cout << fs.rdbuf();  
        fs.close();  
    }  
}  
```  
  
```Output  
Writing to a basic_fstream object...  
```  
  
### <a name="constructors"></a>Constructeurs  
  
|||  
|-|-|  
|[basic_fstream](#basic_fstream)|Construit un objet de type `basic_fstream`.|  
  
### <a name="member-functions"></a>Fonctions membres  
  
|||  
|-|-|  
|[close](#close)|Ferme un fichier.|  
|[is_open](#is_open)|Détermine si un fichier est ouvert.|  
|[open](#open)|Ouvre un fichier.|  
|[rdbuf](#rdbuf)|Retourne l’adresse de la mémoire tampon de flux stockée, de type pointeur à [basic_filebuf](../standard-library/basic-filebuf-class.md)< `Elem`, `Tr`>.|  
|[swap](#swap)|Échange le contenu de cet objet avec le contenu d'un autre objet `basic_fstream`.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<fstream>  
  
 **Espace de noms :** std  
  
##  <a name="basic_fstream"></a>  basic_fstream::basic_fstream  
 Construit un objet de type `basic_fstream`.  
  
```  
basic_fstream();

explicit basic_fstream(
    const char* _Filename,  
    ios_base::openmode _Mode = ios_base::in | ios_base::out,  
    int _Prot = (int)ios_base::_Openprot);

explicit basic_fstream(
    const wchar_t* _Filename,  
    ios_base::openmode _Mode = ios_base::in | ios_base::out,  
    int _Prot = (int)ios_base::_Openprot);

basic_fstream(basic_fstream&& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Filename`  
 Nom du fichier à ouvrir.  
  
 `_Mode`  
 Une des énumérations dans [ios_base::openmode](../standard-library/ios-base-class.md#openmode).  
  
 `_Prot`  
 Protection d’ouverture de fichier par défaut, équivalente au paramètre `shflag` dans [_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md).  
  
### <a name="remarks"></a>Notes  
 Le premier constructeur initialise la classe de base en appelant [basic_iostream](../standard-library/basic-iostream-class.md)( **sb**), où **sb** est l’objet stocké de classe [basic_filebuf](../standard-library/basic-filebuf-class.md)\<**Elem**, **Tr**>. Il initialise également **sb** en appelant `basic_filebuf`\< **Elem**, **Tr**>.  
  
 Les deuxième et troisième constructeurs initialisent la classe de base en appelant `basic_iostream`( **sb**). Ils initialisent également **sb** en appelant `basic_filebuf`\< **Elem**, **Tr**>, puis **sb.**[open](../standard-library/basic-filebuf-class.md#open)(_ *Filename*, `_Mode`). Si cette dernière fonction retourne un pointeur null, le constructeur appelle [setstate](../standard-library/basic-ios-class.md#setstate)( **failbit**).  
  
 Le quatrième constructeur initialise l’objet avec le contenu de `right`, traité comme une référence rvalue.  
  
### <a name="example"></a>Exemple  
  Consultez [streampos](../standard-library/ios-typedefs.md#streampos) pour obtenir un exemple qui utilise `basic_fstream`.  
  
##  <a name="close"></a>  basic_fstream::close  
 Ferme un fichier.  
  
```  
void close();
```  
  
### <a name="remarks"></a>Notes  
 La fonction membre appelle [rdbuf](#rdbuf)**->** [close](../standard-library/basic-filebuf-class.md#close).  
  
### <a name="example"></a>Exemple  
  Consultez [basic_filebuf::close](../standard-library/basic-filebuf-class.md#close) pour obtenir un exemple d’utilisation de **close**.  
  
##  <a name="is_open"></a>  basic_fstream::is_open  
 Détermine si un fichier est ouvert.  
  
```  
bool is_open() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si le fichier est ouvert, **false** dans le cas contraire.  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne [rdbuf](#rdbuf)**->**[is_open](../standard-library/basic-filebuf-class.md#is_open).  
  
### <a name="example"></a>Exemple  
  Consultez [basic_filebuf::is_open](../standard-library/basic-filebuf-class.md#is_open) pour obtenir un exemple d’utilisation de `is_open`.  
  
##  <a name="open"></a>  basic_fstream::open  
 Ouvre un fichier.  
  
```  
void open(
    const char* _Filename,  
    ios_base::openmode _Mode = ios_base::in | ios_base::out,  
    int _Prot = (int)ios_base::_Openprot);

void open(
    const char* _Filename,  
    ios_base::openmode _Mode);

void open(
    const wchar_t* _Filename,  
    ios_base::openmode _Mode = ios_base::in | ios_base::out,  
    int _Prot = (int)ios_base::_Openprot);

void open(
    const wchar_t* _Filename,  
    ios_base::openmode _Mode);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Filename`  
 Nom du fichier à ouvrir.  
  
 `_Mode`  
 Une des énumérations dans [ios_base::openmode](../standard-library/ios-base-class.md#openmode).  
  
 `_Prot`  
 Protection d’ouverture de fichier par défaut, équivalente au paramètre `shflag` dans [_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md).  
  
### <a name="remarks"></a>Notes  
 La fonction membre appelle [rdbuf](#rdbuf) **->** [open](../standard-library/basic-filebuf-class.md#open)(_ *Filename*, `_Mode`). Si cette fonction retourne un pointeur null, la fonction appelle [setstate](../standard-library/basic-ios-class.md#setstate)( **failbit**).  
  
### <a name="example"></a>Exemple  
  Consultez [basic_filebuf::open](../standard-library/basic-filebuf-class.md#open) pour obtenir un exemple d’utilisation d’**open**.  
  
##  <a name="op_eq"></a>  basic_fstream::operator=  
 Assigne à cet objet le contenu d'un objet de flux spécifié. Il s'agit d'une assignation de déplacement qui implique une rvalue qui ne laisse pas de copie.  
  
```  
basic_fstream& operator=(basic_fstream&& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `right`  
 Référence lvalue à un objet `basic_fstream`.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne `*this`.  
  
### <a name="remarks"></a>Notes  
 L'opérateur membre remplace le contenu de l'objet à l'aide du contenu de `right`, traité comme une référence rvalue.  
  
##  <a name="rdbuf"></a>  basic_fstream::rdbuf  
 Retourne l’adresse de la mémoire tampon de flux stockée, de type pointeur à [basic_filebuf](../standard-library/basic-filebuf-class.md)\< **Elem**, **Tr**>.  
  
```  
basic_filebuf<Elem, Tr> *rdbuf() const 
```  
  
### <a name="return-value"></a>Valeur de retour  
 Adresse de la mémoire tampon de flux stockée.  
  
### <a name="example"></a>Exemple  
  Consultez [basic_filebuf::close](../standard-library/basic-filebuf-class.md#close) pour obtenir un exemple d’utilisation de `rdbuf`.  
  
##  <a name="swap"></a>  basic_fstream::swap  
 Échange le contenu de deux objets `basic_fstream`.  
  
```  
void swap(basic_fstream& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `right`  
 Référence `lvalue` à un objet `basic_fstream`.  
  
### <a name="remarks"></a>Notes  
 La fonction membre échange le contenu de cet objet avec celui de `right`.  
  
## <a name="see-also"></a>Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream, programmation](../standard-library/iostream-programming.md)   
 [iostreams, conventions](../standard-library/iostreams-conventions.md)



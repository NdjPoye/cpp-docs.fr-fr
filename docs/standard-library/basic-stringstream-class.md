---
title: basic_stringstream, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- basic_stringstream
- sstream/std::basic_stringstream
- sstream/std::basic_stringstream::allocator_type
- sstream/std::basic_stringstream::rdbuf
- sstream/std::basic_stringstream::str
dev_langs:
- C++
helpviewer_keywords:
- basic_stringstream class
ms.assetid: 49629814-ca37-45c5-931b-4ff894e6ebd2
caps.latest.revision: 19
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
ms.openlocfilehash: cbc938c20a408d721d44877295dc84fc40d04e28
ms.contentlocale: fr-fr
ms.lasthandoff: 04/29/2017

---
# <a name="basicstringstream-class"></a>basic_stringstream, classe
Décrit un objet qui contrôle l’insertion et l’extraction d’éléments et d’objets codés à l’aide d’une mémoire tampon de flux de classe [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`>.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <class Elem, class Tr = char_traits<Elem>, class Alloc = allocator<Elem>>  
class basic_stringstream : public basic_iostream<Elem, Tr>  
```  
  
#### <a name="parameters"></a>Paramètres  
 `Alloc`  
 Classe allocator.  
  
 `Elem`  
 Type de l'élément de base de la chaîne.  
  
 *Tr*  
 Caractéristique spécialisée sur l'élément de base de la chaîne.  
  
## <a name="remarks"></a>Notes  
 La classe de modèle décrit un objet qui contrôle l’insertion et l’extraction d’éléments et d’objets codés à l’aide d’une mémoire tampon de flux de classe [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`>, avec des éléments de type **Elem**, dont les caractéristiques sont déterminées par la classe **Tr** et dont les éléments sont alloués par un allocateur de classe `Alloc`. L’objet stocke un objet de classe basic_stringbuf<**Elem**, **Tr**, `Alloc`>.  
  
### <a name="constructors"></a>Constructeurs  
  
|||  
|-|-|  
|[basic_stringstream](#basic_stringstream)|Construit un objet de type `basic_stringstream`.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[allocator_type](#allocator_type)|Le type est un synonyme du paramètre de modèle `Alloc`.|  
  
### <a name="member-functions"></a>Fonctions membres  
  
|||  
|-|-|  
|[rdbuf](#rdbuf)|Retourne l’adresse de la mémoire tampon de flux stockée de type `pointer` à [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< `Elem`, `Tr`, `Alloc`>.|  
|[str](#str)|Obtient ou définit le texte dans une mémoire tampon de chaîne sans modifier la position d'écriture.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<sstream>  
  
 **Espace de noms :** std  
  
##  <a name="allocator_type"></a>  basic_stringstream::allocator_type  
 Le type est un synonyme du paramètre de modèle `Alloc`.  
  
```  
typedef Alloc allocator_type;  
```  
  
##  <a name="basic_stringstream"></a>  basic_stringstream::basic_stringstream  
 Construit un objet de type `basic_stringstream`.  
  
```  
explicit basic_stringstream(ios_base::openmode _Mode = ios_base::in | ios_base::out);

explicit basic_stringstream(const basic_string<Elem, Tr, Alloc>& str, ios_base::openmode _Mode = ios_base::in | ios_base::out);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Mode`  
 Une des énumérations dans [ios_base::openmode](../standard-library/ios-base-class.md#openmode).  
  
 `str`  
 Objet de type `basic_string`.  
  
### <a name="remarks"></a>Notes  
 Le premier constructeur initialise la classe de base en appelant [basic_ostream](../standard-library/basic-iostream-class.md)( **sb**), où **sb** est l’objet stocké de classe [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`>. Il initialise également **sb** en appelant basic_stringbuf< **Elem**, **Tr**, `Alloc`>( `_Mode`).  
  
 Le deuxième constructeur initialise la classe de base en appelant basic_ostream( **sb**). Il initialise également **sb** en appelant basic_stringbuf< **Elem**, **Tr**, `Alloc`>(_ *Str*, `_Mode`).  
  
##  <a name="rdbuf"></a>  basic_stringstream::rdbuf  
 Retourne l’adresse de la mémoire tampon de flux stockée de type **pointeur** à [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`>.  
  
```  
basic_stringbuf<Elem, Tr, Alloc> *rdbuf() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne l’adresse de la mémoire tampon de flux stockée de type **pointeur** vers basic_stringbuf< **Elem**, **Tr**, `Alloc`>.  
  
### <a name="example"></a>Exemple  
  Consultez [basic_filebuf::close](../standard-library/basic-filebuf-class.md#close) pour obtenir un exemple d’utilisation de `rdbuf`.  
  
##  <a name="str"></a>  basic_stringstream::str  
 Obtient ou définit le texte dans une mémoire tampon de chaîne sans modifier la position d'écriture.  
  
```  
basic_string<Elem, Tr, Alloc> str() const;

 
void str(
    const basic_string<Elem, Tr, Alloc>& _Newstr);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Newstr`  
 La nouvelle chaîne.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne un objet de classe [basic_string](../standard-library/basic-string-class.md)< **Elem**, **Tr**, `Alloc`> dont la séquence contrôlée est une copie de la séquence contrôlée par **\*this**.  
  
### <a name="remarks"></a>Notes  
 La première fonction membre retourne [rdbuf](#rdbuf) -> [str](../standard-library/basic-stringbuf-class.md#str). La deuxième fonction membre appelle `rdbuf` -> **str**( `_Newstr`).  
  
### <a name="example"></a>Exemple  
  Consultez [basic_stringbuf::str](../standard-library/basic-stringbuf-class.md#str) pour obtenir un exemple d’utilisation de **str**.  
  
## <a name="see-also"></a>Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream, programmation](../standard-library/iostream-programming.md)   
 [iostreams, conventions](../standard-library/iostreams-conventions.md)



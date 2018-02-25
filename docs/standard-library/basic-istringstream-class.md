---
title: basic_istringstream, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- sstream/std::basic_istringstream
- sstream/std::basic_istringstream::allocator_type
- sstream/std::basic_istringstream::rdbuf
- sstream/std::basic_istringstream::str
- sstream/std::basic_istringstream::swap
dev_langs:
- C++
helpviewer_keywords:
- std::basic_istringstream [C++]
- std::basic_istringstream [C++], allocator_type
- std::basic_istringstream [C++], rdbuf
- std::basic_istringstream [C++], str
- std::basic_istringstream [C++], swap
ms.assetid: 1d5bb4b5-793d-4833-98e5-14676c451915
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6956b4708061c5eb18ec2adf1570920980dd17e1
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="basicistringstream-class"></a>basic_istringstream, classe
Décrit un objet qui contrôle l’extraction d’éléments et d’objets codés à partir d’une mémoire tampon de flux de classe [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`>.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <class Elem, class Tr = char_traits<Elem>, class Alloc = allocator<Elem>>  
class basic_istringstream : public basic_istream<Elem, Tr>  
```  
  
#### <a name="parameters"></a>Paramètres  
 `Alloc`  
 Classe allocator.  
  
 `Elem`  
 Type de l'élément de base de la chaîne.  
  
 *Tr*  
 Caractéristique spécialisée sur l'élément de base de la chaîne.  
  
## <a name="remarks"></a>Notes  
 La classe de modèle décrit un objet qui contrôle l’extraction d’éléments et d’objets codés à partir d’une mémoire tampon de flux de classe [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`>, avec des éléments de type **Elem**, dont les caractéristiques sont déterminées par la classe **Tr** et dont les éléments sont alloués par un allocateur de classe `Alloc`. L’objet stocke un objet de classe basic_stringbuf<**Elem**, **Tr**, `Alloc`>.  
  
### <a name="constructors"></a>Constructeurs  
  
|||  
|-|-|  
|[basic_istringstream](#basic_istringstream)|Construit un objet de type `basic_istringstream`.|  
  
### <a name="typedefs"></a>Typedef  
  
|||  
|-|-|  
|[allocator_type](#allocator_type)|Le type est un synonyme du paramètre de modèle `Alloc`.|  
  
### <a name="member-functions"></a>Fonctions membres  
  
|||  
|-|-|  
|[rdbuf](#rdbuf)|Retourne l’adresse de la mémoire tampon de flux stockée de type `pointer` à [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< `Elem`, `Tr`, `Alloc`>.|  
|[str](#str)|Obtient ou définit le texte dans une mémoire tampon de chaîne sans modifier la position d'écriture.|  
|[swap](#swap)|Échange les valeurs de cet objet `basic_istringstream` avec celles de l'objet fourni.|  
  
### <a name="operators"></a>Opérateurs  
  
|||  
|-|-|  
|[operator=](#op_eq)|Assigne les valeurs à cet objet `basic_istringstream` à partir du paramètre d'objet.|  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** \<sstream>  
  
 **Espace de noms :** std  
  
##  <a name="allocator_type"></a>  basic_istringstream::allocator_type  
 Le type est un synonyme du paramètre de modèle `Alloc`.  
  
```  
typedef Alloc allocator_type;  
```  
  
##  <a name="basic_istringstream"></a>  basic_istringstream::basic_istringstream  
 Construit un objet de type `basic_istringstream`.  
  
```  
explicit basic_istringstream(
    ios_base::openmode _Mode = ios_base::in);

explicit basic_istringstream(
    const basic_string<Elem, Tr, Alloc>& str,  
    ios_base::openmode _Mode = ios_base::in);

basic_istringstream(
    basic_istringstream&& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Mode`  
 Une des énumérations dans [ios_base::openmode](../standard-library/ios-base-class.md#openmode).  
  
 `str`  
 Objet de type `basic_string`.  
  
 `right`  
 Référence rvalue d’un objet `basic_istringstream`.  
  
### <a name="remarks"></a>Notes  
 Le premier constructeur initialise la classe de base en appelant [basic_istream](../standard-library/basic-istream-class.md)( `sb`), où `sb` est l’objet stocké de classe [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< `Elem`, `Tr`, `Alloc`>. Il initialise également `sb` en appelant `basic_stringbuf`< `Elem`, `Tr`, `Alloc`>( `_Mode` &#124; `ios_base::in`).  
  
 Le deuxième constructeur initialise la classe de base en appelant `basic_istream(sb)`. Il initialise également `sb` en appelant `basic_stringbuf`< `Elem`, `Tr`, `Alloc`>( `str`, `_Mode` &#124; `ios_base::in`).  
  
 Le troisième constructeur initialise l’objet avec le contenu de `right`, traité comme une référence rvalue.  
  
##  <a name="op_eq"></a>  basic_istringstream::operator=  
 Assigne les valeurs à cet objet `basic_istringstream` à partir du paramètre d'objet.  
  
```  
basic_istringstream& operator=(basic_istringstream&& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `right`  
 Référence rvalue à un objet `basic_istringstream`.  
  
### <a name="remarks"></a>Notes  
 L'opérateur membre remplace le contenu de l'objet par le contenu de `right`, traité comme une assignation de déplacement de référence rvalue.  
  
##  <a name="rdbuf"></a>  basic_istringstream::rdbuf  
 Retourne l’adresse de la mémoire tampon de flux stockée de type **pointeur** à [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`>.  
  
```  
basic_stringbuf<Elem, Tr, Alloc> *rdbuf() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne l’adresse de la mémoire tampon de flux stockée de type **pointeur** vers basic_stringbuf< **Elem**, **Tr**, `Alloc`>.  
  
### <a name="example"></a>Exemple  
  Consultez [basic_filebuf::close](../standard-library/basic-filebuf-class.md#close) pour obtenir un exemple d’utilisation de `rdbuf`.  
  
##  <a name="str"></a>  basic_istringstream::str  
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
  
##  <a name="swap"></a>  basic_istringstream::swap  
 Échange les valeurs de deux objets `basic_istringstream`.  
  
```  
void swap(basic_istringstream& right);
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`right`|Référence `lvalue` à un objet `basic_istringstream`.|  
  
### <a name="remarks"></a>Notes  
 La fonction membre remplace les valeurs de cet objet et les valeurs de `right`.  
  
## <a name="see-also"></a>Voir aussi  
 [Sécurité des threads dans la bibliothèque C++ Standard](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream, programmation](../standard-library/iostream-programming.md)   
 [iostreams, conventions](../standard-library/iostreams-conventions.md)


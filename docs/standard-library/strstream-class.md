---
title: strstream, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- strstream
- strstream/std::strstream::freeze
- strstream/std::strstream::pcount
- strstream/std::strstream::rdbuf
- strstream/std::strstream::str
dev_langs:
- C++
helpviewer_keywords:
- strstream class
ms.assetid: 63f3be31-9e36-42b1-9715-a474a5997e2a
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: a1d7d7799e1338c72404f5bcdb9d06e9bac763e5
ms.contentlocale: fr-fr
ms.lasthandoff: 04/29/2017

---
# <a name="strstream-class"></a>strstream, classe
Décrit un objet qui contrôle l’insertion et l’extraction d’éléments et d’objets encodés à l’aide d’une mémoire tampon de flux de classe [strstreambuf](../standard-library/strstreambuf-class.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```
class strstream : public iostream
```  
  
## <a name="remarks"></a>Notes  
 L'objet stocke un objet de classe `strstreambuf`.  
  
> [!NOTE]
>  Cette classe est dépréciée. Utilisez plutôt [stringstream](../standard-library/sstream-typedefs.md#stringstream) ou [wstringstream](../standard-library/sstream-typedefs.md#wstringstream).  
  
### <a name="constructors"></a>Constructeurs  
  
|||  
|-|-|  
|[strstream](#strstream)|Construit un objet de type `strstream`.|  
  
### <a name="member-functions"></a>Fonctions membres  
  
|||  
|-|-|  
|[freeze](#freeze)|Fait en sorte qu'une mémoire tampon de flux soit indisponible via des opérations de mémoire tampon de flux.|  
|[pcount](#pcount)|Retourne le nombre d'éléments écrits dans la séquence contrôlée.|  
|[rdbuf](#rdbuf)|Retourne un pointeur vers l'objet `strstreambuf` associé au flux.|  
|[str](#str)|Appelle [freeze](../standard-library/strstreambuf-class.md#freeze), puis retourne un pointeur vers le début de la séquence contrôlée.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<strstream>  
  
 **Espace de noms :** std  
  
##  <a name="freeze"></a>  strstream::freeze  
 Fait en sorte qu'une mémoire tampon de flux soit indisponible via des opérations de mémoire tampon de flux.  
  
```
void freeze(bool _Freezeit = true);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Freezeit`  
 `bool` indiquant si vous souhaitez que le flux soit gelé.  
  
### <a name="remarks"></a>Notes  
 La fonction membre appelle [rdbuf](#rdbuf) -> [freeze](../standard-library/strstreambuf-class.md#freeze)(_ *Freezeit*).  
  
### <a name="example"></a>Exemple  
  Consultez la page [strstreambuf::freeze](../standard-library/strstreambuf-class.md#freeze) pour obtenir un exemple qui utilise **freeze**.  
  
##  <a name="pcount"></a>  strstream::pcount  
 Retourne le nombre d'éléments écrits dans la séquence contrôlée.  
  
```
streamsize pcount() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Nombre d’éléments écrits dans la séquence contrôlée.  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne [rdbuf](#rdbuf) -> [pcount](../standard-library/strstreambuf-class.md#pcount).  
  
### <a name="example"></a>Exemple  
  Pour obtenir un exemple d’utilisation de pcount, consultez [strstreambuf::pcount](../standard-library/strstreambuf-class.md#pcount).  
  
##  <a name="rdbuf"></a>  strstream::rdbuf  
 Retourne un pointeur vers l’objet strstreambuf associé au flux.  
  
```
strstreambuf *rdbuf() const
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers l’objet strstreambuf associé au flux.  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne l’adresse de la mémoire tampon de flux stockée de type pointeur (**pointer**) vers [strstreambuf](../standard-library/strstreambuf-class.md).  
  
### <a name="example"></a>Exemple  
  Pour obtenir un exemple qui utilise `rdbuf`, consultez [strstreambuf::pcount](../standard-library/strstreambuf-class.md#pcount).  
  
##  <a name="str"></a>  strstream::str  
 Appelle [freeze](../standard-library/strstreambuf-class.md#freeze), puis retourne un pointeur vers le début de la séquence contrôlée.  
  
```
char *str();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers le début de la séquence contrôlée.  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne [rdbuf](#rdbuf) -> [str](../standard-library/strstreambuf-class.md#str).  
  
### <a name="example"></a>Exemple  
  Pour obtenir un exemple qui utilise **str**, consultez [strstreambuf::str](../standard-library/strstreambuf-class.md#str).  
  
##  <a name="strstream"></a>  strstream::strstream  
 Construit un objet de type `strstream`.  
  
```
strstream();

strstream(char* ptr,
    streamsize count,
    ios_base::openmode _Mode = ios_base::in | ios_base::out);
```  
  
### <a name="parameters"></a>Paramètres  
 `count`  
 Taille de la mémoire tampon.  
  
 `_Mode`  
 Mode d’entrée et de sortie de la mémoire tampon. Pour plus d’informations, consultez [ios_base::openmode](../standard-library/ios-base-class.md#openmode).  
  
 `ptr`  
 Mémoire tampon.  
  
### <a name="remarks"></a>Notes  
 Les deux constructeurs initialisent la classe de base en appelant [streambuf](../standard-library/streambuf-typedefs.md#streambuf)( **sb**), où **sb** est l’objet stocké de classe [strstreambuf](../standard-library/strstreambuf-class.md). Le premier constructeur initialise également **sb** en appelant [strstreambuf](../standard-library/strstreambuf-class.md#strstreambuf). Le deuxième constructeur initialise la classe de base d’une des deux façons suivantes :  
  
-   Si `_Mode` & **ios_base::app**== 0, `ptr` doit désigner le premier élément d’un tableau d’éléments `count`, et le constructeur appelle `strstreambuf`( `ptr`, `count`, `ptr`).  
  
-   Sinon, `ptr` doit désigner le premier élément d’un tableau d’éléments count qui contient une chaîne C dont le premier élément est désigné par `ptr`, et le constructeur appelle `strstreambuf`( `ptr`, `count`, `ptr` + `strlen`( `ptr`) ).  
  
## <a name="see-also"></a>Voir aussi  
 [iostream](../standard-library/istream-typedefs.md#iostream)   
 [Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream, programmation](../standard-library/iostream-programming.md)   
 [iostreams, conventions](../standard-library/iostreams-conventions.md)





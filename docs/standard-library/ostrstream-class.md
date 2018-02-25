---
title: ostrstream, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- strstream/std::ostrstream::freeze
- strstream/std::ostrstream::pcount
- strstream/std::ostrstream::rdbuf
- strstream/std::ostrstream::str
dev_langs:
- C++
helpviewer_keywords:
- std::ostrstream [C++], freeze
- std::ostrstream [C++], pcount
- std::ostrstream [C++], rdbuf
- std::ostrstream [C++], str
ms.assetid: e2e34679-b266-4728-a8e1-8eda5d400e46
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 93407ae291956c53e4e105b1ffaf0d4eaf85f7b3
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="ostrstream-class"></a>ostrstream, classe
Décrit un objet qui contrôle l’insertion d’éléments et d’objets encodés dans une mémoire tampon de flux de la classe [strstreambuf](../standard-library/strstreambuf-class.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```
class ostrstream : public ostream
```  
  
## <a name="remarks"></a>Notes  
 L'objet stocke un objet de classe `strstreambuf`.  
  
> [!NOTE]
>  Cette classe est dépréciée. Utilisez plutôt [ostringstream](../standard-library/sstream-typedefs.md#ostringstream) ou [wostringstream](../standard-library/sstream-typedefs.md#wostringstream).  
  
### <a name="constructors"></a>Constructeurs  
  
|||  
|-|-|  
|[ostrstream](#ostrstream)|Construit un objet de type `ostrstream`.|  
  
### <a name="member-functions"></a>Fonctions membres  
  
|||  
|-|-|  
|[freeze](#freeze)|Fait en sorte qu'une mémoire tampon de flux soit indisponible via des opérations de mémoire tampon de flux.|  
|[pcount](#pcount)|Retourne le nombre d'éléments écrits dans la séquence contrôlée.|  
|[rdbuf](#rdbuf)|Retourne un pointeur vers l'objet `strstreambuf` associé au flux.|  
|[str](#str)|Appelle [freeze](../standard-library/strstreambuf-class.md#freeze), puis retourne un pointeur vers le début de la séquence contrôlée.|  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** \<strstream>  
  
 **Espace de noms :** std  
  
##  <a name="freeze"></a>  ostrstream::freeze  
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
  Consultez la page [strstream::freeze](../standard-library/strstreambuf-class.md#freeze) pour obtenir un exemple qui utilise **freeze**.  
  
##  <a name="ostrstream"></a>  ostrstream::ostrstream  
 Construit un objet de type `ostrstream`.  
  
```
ostrstream();

ostrstream(char* ptr,
    streamsize count,
    ios_base::openmode _Mode = ios_base::out);
```  
  
### <a name="parameters"></a>Paramètres  
 `ptr`  
 Mémoire tampon.  
  
 `count`  
 Taille de la mémoire tampon en octets.  
  
 `_Mode`  
 Mode d’entrée et de sortie de la mémoire tampon. Pour plus d’informations, consultez [ios_base::openmode](../standard-library/ios-base-class.md#openmode).  
  
### <a name="remarks"></a>Notes  
 Les deux constructeurs initialisent la classe de base en appelant [ostream](../standard-library/ostream-typedefs.md#ostream)( **sb**), où **sb** est l’objet stocké de la classe [strstreambuf](../standard-library/strstreambuf-class.md). Le premier constructeur initialise également **sb** en appelant `strstreambuf`. Le deuxième constructeur initialise la classe de base d’une des deux façons suivantes :  
  
-   Si `_Mode` & **ios_base::app**== 0, `ptr` doit désigner le premier élément d’un tableau d’éléments `count`, et le constructeur appelle `strstreambuf`( `ptr`, `count`, `ptr`).  
  
-   Sinon, `ptr` doit désigner le premier élément d’un tableau d’éléments count qui contient une chaîne C dont le premier élément est désigné par `ptr`, et le constructeur appelle `strstreambuf`( `ptr`, `count`, `ptr` + `strlen`( `ptr`) ).  
  
##  <a name="pcount"></a>  ostrstream::pcount  
 Retourne le nombre d'éléments écrits dans la séquence contrôlée.  
  
```
streamsize pcount() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Nombre d’éléments écrits dans la séquence contrôlée.  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne [rdbuf](#rdbuf) -> [pcount](../standard-library/strstreambuf-class.md#pcount).  
  
### <a name="example"></a>Exemple  
  Pour obtenir un exemple qui utilise `pcount`, consultez [strstream::pcount](../standard-library/strstreambuf-class.md#pcount).  
  
##  <a name="rdbuf"></a>  ostrstream::rdbuf  
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
  
##  <a name="str"></a>  ostrstream::str  
 Appelle [freeze](../standard-library/strstreambuf-class.md#freeze), puis retourne un pointeur vers le début de la séquence contrôlée.  
  
```
char *str();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers le début de la séquence contrôlée.  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne [rdbuf](#rdbuf) -> [str](../standard-library/strstreambuf-class.md#str).  
  
### <a name="example"></a>Exemple  
  Pour obtenir un exemple qui utilise **str**, consultez [strstream::str](../standard-library/strstreambuf-class.md#str).  
  
## <a name="see-also"></a>Voir aussi  
 [ostream](../standard-library/ostream-typedefs.md#ostream)   
 [Sécurité des threads dans la bibliothèque C++ Standard](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream, programmation](../standard-library/iostream-programming.md)   
 [iostreams, conventions](../standard-library/iostreams-conventions.md)




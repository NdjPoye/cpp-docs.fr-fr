---
title: istrstream, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- strstream/std::istrstream::rdbuf
- strstream/std::istrstream::str
dev_langs: C++
helpviewer_keywords: istrstream class
ms.assetid: c2d41c75-bd2c-4437-bd77-5939ce1b97af
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5e3e91e809980f32c839497ac13b4641bf72c8a2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="istrstream-class"></a>istrstream, classe
Décrit un objet qui contrôle l’extraction d’éléments et d’objets encodés à partir d’une mémoire tampon de flux de classe [strstreambuf](../standard-library/strstreambuf-class.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```
class istrstream : public istream
```  
  
## <a name="remarks"></a>Notes  
 L'objet stocke un objet de classe `strstreambuf`.  
  
> [!NOTE]
>  Cette classe est dépréciée. Utilisez plutôt [istringstream](../standard-library/sstream-typedefs.md#istringstream) ou [wistringstream](../standard-library/sstream-typedefs.md#wistringstream).  
  
### <a name="constructors"></a>Constructeurs  
  
|||  
|-|-|  
|[istrstream](#istrstream)|Construit un objet de type `istrstream`.|  
  
### <a name="member-functions"></a>Fonctions membres  
  
|||  
|-|-|  
|[rdbuf](#rdbuf)|Retourne un pointeur vers l'objet `strstreambuf` associé au flux.|  
|[str](#str)|Appelle [freeze](../standard-library/strstreambuf-class.md#freeze), puis retourne un pointeur vers le début de la séquence contrôlée.|  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** \<strstream>  
  
 **Espace de noms :** std  
  
##  <a name="istrstream"></a>  istrstream::istrstream  
 Construit un objet de type `istrstream`.  
  
```
explicit istrstream(
    const char* ptr);

explicit istrstream(
    char* ptr);

istrstream(
    const char* ptr,
    streamsize count);

istrstream(
    char* ptr,
    int count);
```  
  
### <a name="parameters"></a>Paramètres  
 `count`  
 Longueur de la mémoire tampon ( `ptr`).  
  
 `ptr`  
 Contenu avec lequel la mémoire tampon est initialisée.  
  
### <a name="remarks"></a>Notes  
 Tous les constructeurs initialisent la classe de base en appelant [istream](../standard-library/istream-typedefs.md#istream)( **sb**), où **sb** est l’objet stocké de classe [strstreambuf](../standard-library/strstreambuf-class.md). Les deux premiers constructeurs initialisent également **sb** en appelant `strstreambuf`( ( **const**`char` \*) `ptr`, 0 ). Les deux autres constructeurs appellent plutôt `strstreambuf`( ( **const**`char` *) `ptr`, `count` ).  
  
##  <a name="rdbuf"></a>  istrstream::rdbuf  
 Retourne un pointeur vers l’objet strstreambuf associé au flux.  
  
```
strstreambuf *rdbuf() const
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers l’objet strstreambuf associé au flux.  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne l’adresse de la mémoire tampon de flux stockée de type pointeur vers [strstreambuf](../standard-library/strstreambuf-class.md).  
  
### <a name="example"></a>Exemple  
  Pour obtenir un exemple qui utilise `rdbuf`, consultez [strstreambuf::pcount](../standard-library/strstreambuf-class.md#pcount).  
  
##  <a name="str"></a>  istrstream::str  
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
 [istream](../standard-library/istream-typedefs.md#istream)   
 [Sécurité des threads dans la bibliothèque C++ Standard](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream, programmation](../standard-library/iostream-programming.md)   
 [iostreams, conventions](../standard-library/iostreams-conventions.md)




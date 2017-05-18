---
title: basic_iostream, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- istream/std::basic_iostream
- basic_iostream
- istream/std::basic_iostream::swap
dev_langs:
- C++
helpviewer_keywords:
- basic_iostream class
ms.assetid: 294b680b-eb49-4066-8db2-6d52dac9d6e3
caps.latest.revision: 22
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
ms.openlocfilehash: 3a71df6cc23c0c8f4e6faeb39474c363ed1bd412
ms.contentlocale: fr-fr
ms.lasthandoff: 04/29/2017

---
# <a name="basiciostream-class"></a>basic_iostream, classe
Classe de flux qui peut effectuer à la fois l'entrée et la sortie.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <class Elem, class Tr = char_traits<Elem>>  
class basic_iostream : public basic_istream<Elem, Tr>,  
    public basic_ostream<Elem, Tr>  
{  
public:  
    explicit basic_iostream(basic_streambuf<Elem, Tr>* strbuf);

    virtual ~basic_iostream();

};  
```  
  
## <a name="remarks"></a>Notes  
 La classe de modèle décrit un objet qui contrôle les insertions, par le biais de sa classe de base [basic_ostream](../standard-library/basic-ostream-class.md)< `Elem`, `Tr`>, et les extractions, par le biais de sa classe de base [basic_istream](../standard-library/basic-istream-class.md)< `Elem`, `Tr`>. Les deux objets partagent une classe de base virtuelle commune [basic_ios](../standard-library/basic-ios-class.md)< `Elem`, `Tr`>. Ils gèrent également une mémoire tampon de flux commune, avec des éléments de type `Elem`, dont les caractéristiques sont déterminées par la classe `Tr`. Le constructeur initialise ses classes de base avec `basic_istream`( **strbuf**) et `basic_ostream`( **strbuf**).  
  
### <a name="constructors"></a>Constructeurs  
  
|||  
|-|-|  
|[basic_iostream](#basic_iostream)|Créez un objet `basic_iostream`.|  
  
### <a name="member-functions"></a>Fonctions membres  
  
|||  
|-|-|  
|[swap](#swap)|Échange le contenu de l'objet `basic_iostream` fourni avec le contenu de cet objet.|  
  
### <a name="operators"></a>Opérateurs  
  
|||  
|-|-|  
|[operator=](#op_eq)|Assigne la valeur d'un objet `basic_iostream` spécifié à cet objet. Il s'agit d'une assignation de déplacement impliquant une `rvalue` qui ne laisse pas de copie.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<istream>  
  
 **Espace de noms :** std  
  
##  <a name="basic_iostream"></a>  basic_iostream::basic_iostream  
 Créez un objet `basic_iostream`.  
  
```  
explicit basic_iostream(basic_streambuf<Elem, Tr>* strbuf);

basic_iostream(basic_iostream&& right);

basic_iostream();
```  
  
### <a name="parameters"></a>Paramètres  
 `strbuf`  
 Objet `basic_streambuf` existant.  
  
 `right`  
 Objet `basic_iostream` existant utilisé pour construire un nouveau `basic_iostream`.  
  
### <a name="remarks"></a>Notes  
 Le premier constructeur initialise les objets de base par l’intermédiaire de `basic_istream(strbuf)` et `basic_ostream(strbuf)`.  
  
 Le deuxième constructeur initialise les objets de base en appelant `move(right)`.  
  
##  <a name="op_eq"></a>  basic_iostream::operator=  
 Assigne la valeur d'un objet `basic_iostream` spécifié à cet objet. Il s'agit d'une assignation de déplacement qui implique une rvalue qui ne laisse pas de copie.  
  
```  
basic_iostream& operator=(basic_iostream&& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `right`  
 Référence `rvalue` à un objet `basic_iostream` à partir duquel effectuer l'assignation.  
  
### <a name="remarks"></a>Remarques  
 L’opérateur membre appelle `swap(right)`.  
  
##  <a name="swap"></a>  basic_iostream::swap  
 Échange le contenu de l'objet `basic_iostream` fourni avec le contenu de cet objet.  
  
```  
void swap(basic_iostream& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `right`  
 Objet `basic_iostream` à échanger.  
  
### <a name="remarks"></a>Remarques  
 La fonction membre appelle `swap(right)`.  
  
## <a name="see-also"></a>Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream, programmation](../standard-library/iostream-programming.md)   
 [iostreams, conventions](../standard-library/iostreams-conventions.md)



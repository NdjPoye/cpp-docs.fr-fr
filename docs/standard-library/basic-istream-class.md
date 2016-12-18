---
title: "basic_istream, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "basic_istream"
  - "istream/std::basic_istream"
  - "std::basic_istream"
  - "std.basic_istream"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "basic_istream (classe)"
ms.assetid: c7c27111-de6d-42b4-95a3-a7e65259bf17
caps.latest.revision: 21
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# basic_istream, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Décrit un objet qui contrôle l'extraction d'éléments et d'objets encodés à partir d'une mémoire tampon de flux avec des éléments de type `Elem`, également appelé [char\_type](../Topic/basic_ios::char_type.md), dont les caractéristiques sont déterminées par la classe *Tr*, également appelée [traits\_type](../Topic/basic_ios::traits_type.md).  
  
## Syntaxe  
  
```  
  
     template <class   
     Elem  
     , class   
     Tr  
      = char  
     _  
     traits<  
     Elem  
     > >  
class basic_istream  
   : virtual public basic_ios<Elem, Tr>  
```  
  
## Notes  
 La plupart des fonctions membres qui surchargent [operator\>\>](../Topic/basic_istream::operator%3E%3E.md) sont des fonctions d'entrée mises en forme.  Elles suivent le modèle :  
  
```  
iostate state = goodbit;  
const sentry ok(*this);  
if (ok)  
    {try  
        {<extract elements and convert  
        accumulate flags in state  
        store a successful conversion> }  
    catch (...)  
        {try  
            {setstate(badbit); }  
        catch (...)  
            {}  
        if ((exceptions( ) & badbit) != 0)  
            throw; }}  
setstate(state);  
return (*this);  
```  
  
 De nombreuses autres fonctions membres sont des fonctions d'entrée non mise en forme.  Elles suivent le modèle :  
  
```  
iostate state = goodbit;  
count = 0;    // the value returned by gcount  
const sentry ok(*this, true);  
if (ok)  
    {try  
        {<extract elements and deliver  
        count extracted elements in count  
        accumulate flags in state> }  
    catch (...)  
        {try  
            {setstate(badbit); }  
        catch (...)  
            {}  
        if ((exceptions( ) & badbit) != 0)  
            throw; }}  
setstate(state);  
```  
  
 Les deux groupes de fonctions appellent [setstate](../Topic/basic_ios::setstate.md)\(**eofbit**\) s'ils rencontrent la fin du fichier lors de l'extraction d'éléments.  
  
 Un objet de la classe `basic_istream`\<`Elem`, *Tr*\> stocke :  
  
-   Un objet de base public virtuel de la classe [basic\_ios](../standard-library/basic-ios-class.md)\<`Elem`, *Tr*\>`.`  
  
-   Nombre d'extractions pour la dernière opération d'entrée non mise en forme \(appelé **count** dans le code précédent\).  
  
## Exemple  
 Consultez l'exemple pour la [basic\_ifstream, classe](../standard-library/basic-ifstream-class.md) pour en savoir plus sur les flux d'entrée.  
  
### Constructeurs  
  
|||  
|-|-|  
|[basic\_istream](../Topic/basic_istream::basic_istream.md)|Construit un objet de type `basic_istream`.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[gcount](../Topic/basic_istream::gcount.md)|Retourne le nombre de caractères lus au cours de la dernière entrée non mise en forme.|  
|[get](../Topic/basic_istream::get.md)|Lit un ou plusieurs caractères dans le flux d'entrée.|  
|[getline](../Topic/basic_istream::getline.md)|Lit une ligne dans le flux d'entrée.|  
|[ignorer](../Topic/basic_istream::ignore.md)|Ignore un certain nombre d'éléments à partir de la position de lecture actuelle.|  
|[peek](../Topic/basic_istream::peek.md)|Retourne le caractère suivant à lire.|  
|[putback](../Topic/basic_istream::putback.md)|Place un caractère spécifié dans le flux.|  
|[read](../Topic/basic_istream::read.md)|Lit un nombre spécifié de caractères dans le flux et les stocke dans un tableau.|  
|[readsome](../Topic/basic_istream::readsome.md)|Lire seulement dans la mémoire tampon.|  
|[seekg](../Topic/basic_istream::seekg.md)|Déplace la position de lecture dans un flux.|  
|[sentry](../Topic/basic_istream::sentry.md)|La classe imbriquée décrit un objet dont la déclaration structure les fonctions d'entrée mise en forme et les fonctions d'entrée non mise en forme.|  
|[échange](../Topic/basic_istream::swap.md)|Échange cet objet `basic_istream` pour le paramètre d'objet `basic_istream` fourni.|  
|[sync](../Topic/basic_istream::sync.md)|Synchronise le périphérique d'entrée associé au flux avec la mémoire tampon du flux.|  
|[tellg](../Topic/basic_istream::tellg.md)|Indique la position de lecture actuelle dans le flux.|  
|[unget](../Topic/basic_istream::unget.md)|Replace le dernier caractère lu dans le flux.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[\>\>, opérateur](../Topic/basic_istream::operator%3E%3E.md)|Appelle une fonction sur le flux d'entrée ou lit les données mises en forme dans le flux d'entrée.|  
|[opérateur \=](../Topic/basic_istream::operator=.md)|Affecte le `basic_istream` du côté droit de l'opérateur à cet objet.  Il s'agit d'une assignation de déplacement qui implique une référence `rvalue` qui ne laisse pas de copie.|  
  
## Configuration requise  
 **En\-tête :** \<istream\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream, programmation](../standard-library/iostream-programming.md)   
 [iostreams, conventions](../standard-library/iostreams-conventions.md)
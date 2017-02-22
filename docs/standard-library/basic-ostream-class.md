---
title: "basic_ostream, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::basic_ostream"
  - "std.basic_ostream"
  - "ostream/std::basic_ostream"
  - "basic_ostream"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "basic_ostream (classe)"
ms.assetid: 5baadc65-b662-4fab-8c9f-94457c58cda1
caps.latest.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 24
---
# basic_ostream, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette classe de modèle décrit un objet qui contrôle l'insertion d'éléments et d'objets encodés dans une mémoire tampon de flux avec des éléments de type **Elem**, également appelé [char\_type](../Topic/basic_ios::char_type.md), dont les caractéristiques sont déterminées par la classe **Tr**, également appelée [traits\_type](../Topic/basic_ios::traits_type.md).  
  
## Syntaxe  
  
```  
  
template <class   
_Elem  
, class   
_Tr  
 = char  
_  
traits<Elem> >  
   class basic  
_  
ostream  
       : virtual public basic  
_  
ios<  
_Elem  
,   
_Tr  
>  
  
```  
  
#### Paramètres  
 `_Elem`  
 `char_type`  
  
 `_Tr`  
 `traits_type` du caractère.  
  
## Notes  
 La plupart des fonctions membres qui surchargent [operator\<\<](../Topic/basic_ostream::operator%3C%3C.md) sont des fonctions de sortie mise en forme. Elles suivent le modèle :  
  
```  
iostate state = goodbit;  
const sentry ok( *this );  
if ( ok )  
   {try  
      {<convert and insert elements  
      accumulate flags in state> }  
   catch ( ... )  
      {try  
        {setstate( badbit ); }  
      catch ( ... )  
        {}  
      if ( ( exceptions( ) & badbit ) != 0 )  
        throw; }}  
width( 0 );    // Except for operator<<(Elem)  
setstate( state );  
return ( *this );  
```  
  
 Deux autres fonctions membres sont des fonctions de sortie non mises en forme. Elles suivent le modèle :  
  
```  
iostate state = goodbit;  
const sentry ok( *this );  
if ( !ok )  
   state |= badbit;  
else  
   {try  
      {<obtain and insert elements  
      accumulate flags in state> }  
   catch ( ... )  
      {try  
         {setstate( badbit ); }  
      catch ( ... )  
         {}  
      if ( ( exceptions( ) & badbit ) != 0 )  
         throw; }}  
setstate( state );  
return ( *this );  
```  
  
 Ces deux groupes de fonctions appellent [setstate](../Topic/basic_ios::setstate.md)**\(badbit\)** si elles rencontrent un échec lors de l'insertion d'éléments.  
  
 Un objet de classe basic\_istream \<**Elem**, **Tr**\> stocke seulement un objet de base public virtuel de la classe [basic\_ios](../standard-library/basic-ios-class.md)**\<Elem**, **Tr\>**.  
  
## Exemple  
 Consultez l’exemple de [basic\_ofstream, classe](../standard-library/basic-ofstream-class.md) pour en savoir plus sur les flux de sortie.  
  
### Constructeurs  
  
|||  
|-|-|  
|[basic\_ostream](../Topic/basic_ostream::basic_ostream.md)|Construit un objet `basic_ostream`.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[flush](../Topic/basic_ostream::flush.md)|Vide la mémoire tampon.|  
|[put](../Topic/basic_ostream::put.md)|Place un caractère dans un flux.|  
|[seekp](../Topic/basic_ostream::seekp.md)|Réinitialise la position dans le flux de sortie.|  
|[sentry](../Topic/basic_ostream::sentry.md)|La classe imbriquée décrit un objet dont la déclaration structure les fonctions de sortie mise en forme et les fonctions de sortie non mise en forme.|  
|[swap](../Topic/basic_ostream::operator=.md)|Échange les valeurs de cet objet `basic_ostream` avec celles de l'objet `basic_ostream` fourni.|  
|[tellp](../Topic/basic_ostream::tellp.md)|Indique la position dans le flux de sortie.|  
|[écriture](../Topic/basic_ostream::write.md)|Place des caractères dans un flux.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[opérateur \=](../Topic/basic_ostream::operator=.md)|Affecte la valeur du paramètre d'objet `basic_ostream` fourni à cet objet.|  
|[\<\<, opérateur](../Topic/basic_ostream::operator%3C%3C.md)|Écrit dans le flux.|  
  
## Configuration requise  
 **En\-tête :** \<ostream\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream, programmation](../standard-library/iostream-programming.md)   
 [iostreams, conventions](../standard-library/iostreams-conventions.md)
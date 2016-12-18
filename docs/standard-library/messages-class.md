---
title: "messages, classe | Microsoft Docs"
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
  - "messages"
  - "xlocmes/std::messages"
  - "std.messages"
  - "std::messages"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "messages (classe)"
ms.assetid: c4c71f40-4f24-48ab-9f7c-daccd8d5bd83
caps.latest.revision: 18
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# messages, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette classe de modèle décrit un objet pouvant servir de facette de paramètres régionaux pour récupérer des messages localisés à partir d'un catalogue de messages internationalisés pour des paramètres régionaux donnés.  
  
 Actuellement, lorsque la classe de messages est implémentée, il n'y a aucun message.  
  
## Syntaxe  
  
```  
template <class CharType>  
   class messages : public messages_base;  
```  
  
#### Paramètres  
 `CharType`  
 Type utilisé dans un programme pour encoder des caractères dans des paramètres régionaux spécifiques.  
  
## Notes  
 Comme avec n'importe quelle facette de paramètres régionaux, l'ID d'objet statique possède une valeur stockée initiale de zéro. La première tentative d’accéder à sa valeur stockée stocke une valeur positive unique dans **ID**  
  
 Cette facette ouvre un catalogue de messages définis dans la classe de base messages\_base, récupère les informations requises et ferme le catalogue.  
  
### Constructeurs  
  
|||  
|-|-|  
|[messages](../Topic/messages::messages.md)|Fonction constructeur de facette de message.|  
  
### Typedefs  
  
|||  
|-|-|  
|[char\_type](../Topic/messages::char_type.md)|Type de caractère utilisé pour afficher les messages.|  
|[string\_type](../Topic/messages::string_type.md)|Type qui décrit une chaîne de type `basic_string` qui contient des caractères de type `CharType`.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[fermer](../Topic/messages::close.md)|Ferme le catalogue de messages.|  
|[do\_close](../Topic/messages::do_close.md)|Fonction virtuelle appelée pour fermer le catalogue de messages.|  
|[do\_get](../Topic/messages::do_get.md)|Fonction virtuelle appelée pour récupérer le catalogue de messages.|  
|[do\_open](../Topic/messages::do_open.md)|Fonction virtuelle appelée pour ouvrir le catalogue de messages.|  
|[get](../Topic/messages::get.md)|Récupère le catalogue de messages.|  
|[ouvrir](../Topic/messages::open.md)|Ouvre le catalogue de messages.|  
  
## Configuration requise  
 **En\-tête :** \<locale\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<locale\>](../standard-library/locale.md)   
 [messages\_base, classe](../standard-library/messages-base-class.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)
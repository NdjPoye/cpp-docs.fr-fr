---
title: "time_get, classe | Microsoft Docs"
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
  - "std.time_get"
  - "xloctime/std::time_get"
  - "time_get"
  - "std::time_get"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "time_get (classe)"
ms.assetid: 869d5f5b-dbab-4628-8333-bdea7e272023
caps.latest.revision: 21
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# time_get, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette classe de modèle décrit un objet pouvant servir de facette de paramètres régionaux pour contrôler les conversions de séquences de type `CharType` en valeurs temporelles.  
  
## Syntaxe  
  
```  
template <  
   class CharType,  
   class InputIterator = istreambuf_iterator<CharType>  
> class time_get : public time_base;  
```  
  
#### Paramètres  
 `CharType`  
 Type utilisé dans le cadre d'un programme pour encoder des caractères.  
  
 `InputIterator`  
 Itérateur dont les valeurs temporelles sont lues.  
  
## Notes  
 Comme avec n'importe quelle facette de paramètres régionaux, l'ID d'objet statique possède une valeur stockée initiale de zéro.  La première tentative d'accès à sa valeur stockée entraîne le stockage d'une valeur positive unique dans **id**.  
  
### Constructeurs  
  
|||  
|-|-|  
|[time\_get](../Topic/time_get::time_get.md)|Constructeur des objets de type `time_get`.|  
  
### Typedef  
  
|||  
|-|-|  
|[char\_type](../Topic/time_get::char_type.md)|Type utilisé pour décrire un caractère utilisé par des paramètres régionaux.|  
|[iter\_type](../Topic/time_get::iter_type.md)|Type qui décrit un itérateur d'entrée.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[date\_order](../Topic/time_get::date_order.md)|Retourne l'ordre de date utilisé par une facette.|  
|[do\_date\_order](../Topic/time_get::do_date_order.md)|Fonction membre virtuelle qui est appelée pour retourner l'ordre de date utilisé par une facette.|  
|[do\_get](../Topic/time_get::do_get.md)|Lit, puis convertit des données de caractères en valeur temporelle.|  
|[do\_get\_date](../Topic/time_get::do_get_date.md)|Fonction membre virtuelle appelée pour analyser une chaîne représentant une date générée par le spécificateur `x` pour `strftime`.|  
|[do\_get\_monthname](../Topic/time_get::do_get_monthname.md)|Fonction membre virtuelle appelée pour analyser une chaîne représentant le nom du mois.|  
|[do\_get\_time](../Topic/time_get::do_get_time.md)|Fonction membre virtuelle appelée pour analyser une chaîne représentant une date générée par le spécificateur `X` pour `strftime`.|  
|[do\_get\_weekday](../Topic/time_get::do_get_weekday.md)|Fonction membre virtuelle appelée pour analyser une chaîne représentant le nom du jour de la semaine.|  
|[do\_get\_year](../Topic/time_get::do_get_year.md)|Fonction membre virtuelle appelée pour analyser une chaîne représentant le nom de l'année.|  
|[get](../Topic/time_get::get.md)|Lit une source de données de caractères et convertit ces données en heure, puis stocke cette dernière dans un struct d'heure.|  
|[get\_date](../Topic/time_get::get_date.md)|Analyse une chaîne représentant la date générée par le spécificateur `x` pour `strftime`.|  
|[get\_monthname](../Topic/time_get::get_monthname.md)|Analyse une chaîne représentant le nom du mois.|  
|[get\_time](../Topic/time_get::get_time.md)|Analyse une chaîne représentant la date générée par le spécificateur `X` pour `strftime`.|  
|[get\_weekday](../Topic/time_get::get_weekday.md)|Analyse une chaîne représentant le nom du jour de la semaine.|  
|[get\_year](../Topic/time_get::get_year.md)|Analyse une chaîne représentant le nom de l'année.|  
  
## Configuration requise  
 **En\-tête :** \<locale\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<locale\>](../standard-library/locale.md)   
 [time\_base, classe](../standard-library/time-base-class.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)
---
title: "Sp&#233;cificateurs de type de donn&#233;es et &#233;quivalents | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "types de données (C++), équivalents"
  - "types de données (C++), spécificateurs"
  - "identificateurs, type de données"
  - "types intégraux pour extension de signe"
  - "types simples, noms"
  - "noms de types (C++), simples"
  - "spécificateurs de type (C++), liste"
  - "entiers étendus"
  - "extension zéro"
ms.assetid: 0d4b515a-4f68-4786-83cf-a5d43c7cb6f3
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Sp&#233;cificateurs de type de donn&#233;es et &#233;quivalents
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet ouvrage utilise généralement les formes des spécificateurs de type répertoriées dans le tableau ci\-dessous plutôt que les formes longues, et il suppose que le type `char` est signé par défaut.  Par conséquent, dans l'ensemble de cet ouvrage, `char` est équivalent à **signed char**.  
  
### Spécificateurs de type et équivalents  
  
|Spécificateur de type|Équivalent\(s\)|  
|---------------------------|---------------------|  
|**signed char**1|`char`|  
|**signed int**|**signed**, `int`|  
|**signed short int**|**short**, `signed short`|  
|**signed long int**|**long**, **signed long**|  
|`unsigned char`|—|  
|`unsigned int`|`unsigned`|  
|**unsigned short int**|**unsigned short**|  
|**unsigned long int**|`unsigned long`|  
|**float**|—|  
|`long double`2|—|  
  
 1   Lorsque vous spécifiez le type `char` comme étant non signé par défaut \(en spécifiant l'option \/J du compilateur\), vous ne pouvez pas abréger **signed char** en `char`.  
  
 2   Dans les systèmes d'exploitation 32 bits, le compilateur Microsoft C mappe **long double** sur le type **double**.  
  
 **Section spécifique à Microsoft**  
  
 Vous pouvez spécifier l'option \/J du compilateur pour modifier le type `char` par défaut de signé à non signé.  Lorsque cette option est appliquée, `char` a la même signification que `unsigned char`, et vous devez utiliser le mot clé **signed** pour déclarer une valeur de caractère signée.  Si une valeur `char` est déclarée explicitement comme étant signée, l'option \/J ne l'affecte pas, et la valeur est étendue par un signe lorsqu'elle est élargie à un type `int`.  Le type `char` est étendu par zéro lorsqu'il est élargi au type `int`.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [Spécificateurs de type C](../c-language/c-type-specifiers.md)
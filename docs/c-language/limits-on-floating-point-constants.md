---
title: "Limites des constantes &#224; virgule flottante | Microsoft Docs"
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
  - "constantes, virgule flottante"
  - "FLOAT.H (fichier d'en-tête)"
  - "constantes à virgule flottante, limites"
  - "chiffres à virgule flottante, limites flottantes"
  - "limites, constantes à virgule flottante"
  - "plages, constantes à virgule flottante"
ms.assetid: 2d975868-2af6-45d7-a8af-db79f2c6b67b
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Limites des constantes &#224; virgule flottante
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Le tableau suivant répertorie les limites applicables aux valeurs des constantes à virgule flottante.  Le fichier d'en\-tête FLOAT.H contient ces informations.  
  
### Limites sur les constantes à virgule flottante  
  
|Constante|Signification|Valeur|  
|---------------|-------------------|------------|  
|**FLT\_DIGDBL\_DIGLDBL\_DIG**|Nombre de chiffres, *q*, tel qu'un nombre à virgule flottante avec *q* chiffres décimaux peut être arrondi en une représentation à virgule flottante puis restauré à sa valeur initiale sans perte de précision.|6 15 15|  
|**FLT\_EPSILONDBL\_EPSILONLDBL\_EPSILON**|Plus petit nombre positif *x* tel que *x* \+ 1,0 n'est pas égal à 1,0.|1,192092896e\-07F 2,2204460492503131e\-016 2,2204460492503131e\-016|  
|**FLT\_GUARD**||0|  
|**FLT\_MANT\_DIGDBL\_MANT\_DIGLDBL\_MANT\_DIG**|Nombre de chiffres dans la base spécifiée par **FLT\_RADIX** dans la mantisse à virgule flottante.  La base est 2 ; par conséquent, ces valeurs spécifient des bits.|24 53 53|  
|**FLT\_MAXDBL\_MAXLDBL\_MAX**|Nombre à virgule flottante maximal pouvant être représenté|3,402823466e\+38F 1,7976931348623158e\+308 1,7976931348623158e\+308|  
|**FLT\_MAX\_10\_EXPDBL\_MAX\_10\_EXPLDBL\_MAX\_10\_EXP**|Entier maximal tel que 10 élevé à la puissance de ce nombre est un nombre à virgule flottante pouvant être représenté.|38 308 308|  
|**FLT\_MAX\_EXPDBL\_MAX\_EXPLDBL\_MAX\_EXP**|Entier maximal tel que **FLT\_RADIX** élevé à la puissance de ce nombre est un nombre à virgule flottante pouvant être représenté.|128 1024 1024|  
|**FLT\_MINDBL\_MINLDBL\_MIN**|Valeur positive minimale.|1,175494351e–38F 2,2250738585072014e–308 2,2250738585072014e–308|  
|**FLT\_MIN\_10\_EXPDBL\_MIN\_10\_EXPLDBL\_MIN\_10\_EXP**|Entier négatif minimal tel que 10 élevé à la puissance de ce nombre est un nombre à virgule flottante pouvant être représenté.|–37<br /><br /> –307<br /><br /> –307|  
|**FLT\_MIN\_EXPDBL\_MIN\_EXPLDBL\_MIN\_EXP**|Entier négatif minimal tel que **FLT\_RADIX** élevé à la puissance de ce nombre est un nombre à virgule flottante pouvant être représenté.|–125<br /><br /> –1021<br /><br /> –1021|  
|**FLT\_NORMALIZE**||0|  
|**FLT\_RADIX\_DBL\_RADIX\_LDBL\_RADIX**|Base de représentation d'exposant|2 2 2|  
|**FLT\_ROUNDS\_DBL\_ROUNDS\_LDBL\_ROUNDS**|Mode d'arrondi pour l'addition à virgule flottante|1 \(environ\) 1 \(environ\) 1 \(environ\)|  
  
 Notez que les informations fournies dans le tableau ci\-dessus peuvent différer dans des implémentations futures.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [Constantes à virgule flottante C](../c-language/c-floating-point-constants.md)
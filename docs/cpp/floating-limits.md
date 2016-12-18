---
title: "Limites des valeurs &#224; virgule flottante | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "FLOAT.H (fichier d'en-tête)"
  - "constantes à virgule flottante, limites"
  - "chiffres à virgule flottante, limites flottantes"
  - "limites, constantes à virgule flottante"
  - "plages, constantes à virgule flottante"
ms.assetid: fc718652-1f4c-4ed8-af60-0e769637459c
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Limites des valeurs &#224; virgule flottante
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Le tableau suivant répertorie les limites applicables aux valeurs des constantes à virgule flottante.  Ces limites sont également définies dans le fichier d'en\-tête standard FLOAT.H.  
  
### Limites sur les constantes à virgule flottante  
  
|Constante|Signification|Valeur|  
|---------------|-------------------|------------|  
|FLT\_DIG DBL\_DIG LDBL\_DIG|Nombre de chiffres, q, tel qu'un nombre à virgule flottante avec q chiffres décimaux peut être arrondi en une représentation à virgule flottante puis restauré à sa valeur initiale sans perte de précision.|6 15 15|  
|FLT\_EPSILON DBL\_EPSILON LDBL\_EPSILON|Plus petit nombre positif x tel que x \+ 1,0 n'est pas égal à 1,0.|1,192092896e\-07F 2,2204460492503131e\-016 2,2204460492503131e\-016|  
|FLT\_GUARD||0|  
|FLT\_MANT\_DIG DBL\_MANT\_DIG LDBL\_MANT\_DIG|Nombre de chiffres dans la base spécifiée par FLT\_RADIX dans la mantisse à virgule flottante.  La base est 2 ; par conséquent, ces valeurs spécifient des bits.|24 53 53|  
|FLT\_MAX DBL\_MAX LDBL\_MAX|Nombre à virgule flottante maximal pouvant être représenté.|3,402823466e\+38F 1,7976931348623158e\+308 1,7976931348623158e\+308|  
|FLT\_MAX\_10\_EXP DBL\_MAX\_10\_EXP LDBL\_MAX\_10\_EXP|Entier maximal tel que 10 élevé à la puissance de ce nombre est un nombre à virgule flottante qui peut être représenté.|38 308 308|  
|FLT\_MAX\_EXP DBL\_MAX\_EXP LDBL\_MAX\_EXP|Entier maximal tel que FLT\_RADIX élevé à la puissance de ce nombre est un nombre à virgule flottante qui peut être représenté.|128 1024 1024|  
|FLT\_MIN DBL\_MIN LDBL\_MIN|Valeur positive minimale.|1,175494351e–38F 2,2250738585072014e–308 2,2250738585072014e–308|  
|FLT\_MIN\_10\_EXP DBL\_MIN\_10\_EXP LDBL\_MIN\_10\_EXP|Entier négatif minimal tel que 10 élevé à la puissance de ce nombre est un nombre à virgule flottante qui peut être représenté.|–37<br /><br /> –307<br /><br /> –307|  
|FLT\_MIN\_EXP DBL\_MIN\_EXP LDBL\_MIN\_EXP|Entier négatif minimal tel que FLT\_RADIX élevé à la puissance de ce nombre est un nombre à virgule flottante qui peut être représenté.|–125<br /><br /> –1021<br /><br /> –1021|  
|FLT\_NORMALIZE||0|  
|FLT\_RADIX \_DBL\_RADIX \_LDBL\_RADIX|Base de représentation d'exposant|2 2 2|  
|FLT\_ROUNDS \_DBL\_ROUNDS \_LDBL\_ROUNDS|Mode d'arrondi pour l'addition à virgule flottante.|1 \(environ\) 1 \(environ\) 1 \(environ\)|  
  
> [!NOTE]
>  Les informations contenues dans le tableau peuvent différer dans les versions ultérieures du produit.  
  
## FIN de la section spécifique à Microsoft  
  
## Voir aussi  
 [Limites d'entier](../cpp/integer-limits.md)
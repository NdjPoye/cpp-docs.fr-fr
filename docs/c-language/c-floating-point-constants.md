---
title: "Constantes &#224; virgule flottante C | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "constantes, virgule flottante"
  - "double (type de données), constantes à virgule flottante"
  - "constantes à virgule flottante"
  - "constantes à virgule flottante, à propos des constantes à virgule flottante"
  - "chiffres à virgule flottante, constantes à virgule flottante"
  - "types (C), constantes"
ms.assetid: e1bd9b44-d6ab-470c-93e5-07142c7a2062
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# Constantes &#224; virgule flottante C
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

« Une constante à virgule flottante » est un nombre décimal qui représente un nombre réel signé.  La représentation d'un nombre réel signé inclut une partie entière, une partie fractionnelle, et un exposant.  Utilisez des constantes à virgule flottante pour représenter les valeurs à virgule flottante qui ne peuvent pas être modifiées.  
  
## Syntaxe  
 *Constantes à virgule flottante*:  
 *partie constante\-fractionnelle\-exponentielle* opt *suffixe flottant*opt  
  
 *Séquence de chiffre partie exponentielle suffixe flottant* opt  
  
 *constante\-fractionnelle*:  
 *séquence de chiffres*  opt               **.**  *séquence de chiffres*  
  
 *séquence de chiffres* **.**  
  
 *partie exponentielle*:  
 **e**  *signe*  opt *séquence de chiffres*  
  
 **E**  *signe*  opt *séquence de chiffres*  
  
 *signe* : un de  
 **\+ –**  
  
 *séquence de chiffres*:  
 *digit*  
  
 *chiffre\-séquence de chiffre*  
  
 *suffixe flottant* : un parmi  
 **f l F L**  
  
 Vous pouvez omettre les chiffres avant la virgule décimale \(la partie entière de la valeur\) ou les chiffres après la virgule décimale \(la partie fractionnaire\), mais pas les deux.  Omettez la virgule décimale uniquement si vous incluez un exposant.  Aucun espace blanc ne peut séparer les chiffres ou des caractères de la constante.  
  
 Les exemples suivants montrent des formes des constantes à virgule flottante et d'expressions :  
  
```  
15.75  
1.575E1   /* = 15.75   */  
1575e-2   /* = 15.75   */  
-2.5e-3   /* = -0.0025 */  
25E-4     /* =  0.0025 */  
```  
  
 Les constantes à virgule flottante sont positives à moins qu'elles soient précédées par un signe moins \(**–**\).  Dans ce cas, le signe moins est traité comme opérateur unaire arithmétique de négation.  Les constantes à virgule flottante ont le type **float**, **Double**, ou `long double`.  
  
 Une constante à virgule flottante sans **f**, **F**, **l**, ou suffixe **L** a le type **Double**.  Si la lettre **f** ou **F** est le suffixe, la constante a le type **float**.  Si le suffixe est la lettre **l** ou **L**, elle a le type `long double`.  Par exemple :  
  
```  
100L  /* Has type long double  */  
100F  /* Has type float        */  
```  
  
 Notez que le compilateur C Microsoft mappe **long double** pour le type **Double**.  Consultez [Stockage des types de base](../c-language/storage-of-basic-types.md) pour plus d'informations sur le type **Double**, **float**, et **long**.  
  
 Vous pouvez omettre la partie entière de la constante à virgule flottante, comme indiqué dans les exemples suivants.  Le nombre ,75 peut être exprimé plusieurs manières, notamment :  
  
```  
.0075e2  
0.075e1  
.075e1  
75e-2  
```  
  
## Voir aussi  
 [Constantes C](../c-language/c-constants.md)
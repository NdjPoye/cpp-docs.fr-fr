---
title: "S&#233;curiser les surcharges de mod&#232;le | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES"
  - "_CRT_SECURE_CPP_OVERLOAD_SECURE_NAMES"
  - "_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_CRT_SECURE_CPP_OVERLOAD_SECURE_NAMES"
  - "_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES"
  - "_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT"
  - "sécuriser des surcharges de modèle"
ms.assetid: 562741d0-39c0-485e-8529-73d740f29f8f
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# S&#233;curiser les surcharges de mod&#232;le
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

De nombreuses fonctions CRT sont déconseillées et remplacées par des versions plus récentes et sécurisées \(par exemple, `strcpy_s` est le remplacement le plus sécurisé pour `strcpy`\).  Le CRT fournit des surcharges de modèle afin de faciliter la transition vers des variantes plus sécurisées.  
  
 Par exemple, ce code génère un avertissement car `strcpy` est déconseillée :  
  
 `char szBuf[10];`  
  
 `strcpy(szBuf, "test"); // warning: deprecated`  
  
 Vous pouvez ignorer l'avertissement.  Définissez le symbole `_CRT_SECURE_NO_WARNINGS` pour supprimer l'avertissement, ou mettez à jour le code pour utiliser `strcpy_s`:  
  
 `char szBuf[10];`  
  
 `strcpy_s(szBuf, 10, "test"); // security-enhanced _s function`  
  
 Les surcharges de modèle fournissent des options supplémentaires.  Définir `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` sur 1 permet des surcharges de modèle de fonctions CRT standards qui appellent automatiquement les variantes les plus sécurisées.  Si `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` est 1, alors aucune modification du code n'est nécessaire.  En arrière\-plan, l'appel à `strcpy` sera remplacé par un appel à `strcpy_s` avec l'argument de taille fourni automatiquement.  
  
 `#define _CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES 1`  
  
 `...`  
  
 `char szBuf[10];`  
  
 `strcpy(szBuf, "test"); // ==> strcpy_s(szBuf, 10, "test")`  
  
 `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` n'affecte pas les fonctions qui prennent un nombre, par exemple `strncpy`.  Pour activer des surcharges de modèle pour les fonctions de nombre, définissez `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT` à 1.  Avant cela, toutefois, vérifiez que votre code obtient le nombre de caractères, et non la taille de la mémoire tampon \(une erreur courante\).  De plus, du code qui écrit explicitement un terminateur NULL à la fin de la mémoire tampon après l'appel à la fonction n'est pas nécessaire si la variante sécurisée est appelée.  Si vous avez besoin du comportement de la troncation, consultez [\_TRUNCATE](../c-runtime-library/truncate.md).  
  
> [!NOTE]
>  La macro `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT` nécessite que `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` soit également défini comme 1.  Si `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT` est défini comme étant 1 et `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` est défini avec la valeur 0, l'application n'effectue aucune surcharge de modèle.  
  
 Définir `_CRT_SECURE_CPP_OVERLOAD_SECURE_NAMES` sur 1 permet des surcharges de modèle des variantes sécurisées \(noms finissant par « \_s »\).  Dans ce cas, si `_CRT_SECURE_CPP_OVERLOAD_SECURE_NAMES` est 1, alors une petite modification doit être effectuée au code d'origine :  
  
 `#define _CRT_SECURE_CPP_OVERLOAD_SECURE_NAMES 1`  
  
 `...`  
  
 `char szBuf[10];`  
  
 `strcpy_s(szBuf, "test"); // ==> strcpy_s(szBuf, 10, "test")`  
  
 Seul le nom de la fonction doit être modifié \(en ajoutant "\_s"\) ; la surcharge de modèle prend soin de fournir l'argument de taille.  
  
 Par défaut, `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` et `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT` sont définis comme 0 \(désactivé\) et `_CRT_SECURE_CPP_OVERLOAD_SECURE_NAMES` est défini comme 1 \(activé\).  
  
 Notez que les surcharges de modèle fonctionnent uniquement pour les tables statiques.  Les mémoires tampons allouées dynamiquement requièrent des modifications supplémentaires de code source.  Revisiter les exemples ci\-dessus :  
  
 `#define _CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES 1`  
  
 `...`  
  
 `char *szBuf = (char*)malloc(10);`  
  
 `strcpy(szBuf, "test"); // still deprecated; have to change to`  
  
 `// strcpy_s(szBuf, 10, "test");`  
  
 Et ceci:  
  
 `#define _CRT_SECURE_CPP_OVERLOAD_SECURE_NAMES 1`  
  
 `...`  
  
 `char *szBuf = (char*)malloc(10);`  
  
 `strcpy_s(szBuf, "test"); // doesn't compile; have to change to`  
  
 `// strcpy_s(szBuf, 10, "test");`  
  
## Voir aussi  
 [Fonctionnalités de sécurité dans le CRT](../c-runtime-library/security-features-in-the-crt.md)   
 [Fonctions de bibliothèque CRT](../c-runtime-library/crt-library-features.md)
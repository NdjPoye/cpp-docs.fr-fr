---
title: "Catégories de paramètres régionaux | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- LC_MAX
- LC_MIN
- LC_MONETARY
- LC_TIME
- LC_NUMERIC
- LC_COLLATE
- LC_CTYPE
- LC_ALL
dev_langs: C++
helpviewer_keywords:
- LC_MIN constant
- LC_MONETARY constant
- LC_CTYPE constant
- locale constants
- LC_MAX constant
- LC_ALL constant
- LC_TIME constant
- LC_NUMERIC constant
- LC_COLLATE constant
ms.assetid: 868f1493-fe5d-4722-acab-bfcd374a063a
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8e2188dc477a81477b65db22bcd06390a4b6773c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="locale-categories"></a>Catégories de paramètres régionaux
## <a name="syntax"></a>Syntaxe  
  
```  
  
#include <locale.h>  
  
```  
  
## <a name="remarks"></a>Notes  
 Les catégories de paramètres régionaux sont des constantes manifestes utilisées par les routines de localisation pour spécifier dans quelle portion des informations de paramètres régionaux d’un programme les informations seront utilisées. Les paramètres régionaux font référence à la localité (ou au pays/à la région) pour laquelle certains aspects de votre programme peuvent être personnalisés. Les zones dépendant des paramètres régionaux comprennent par exemple la mise en forme des dates et le format d'affichage des valeurs monétaires.  
  
|Catégorie de paramètres régionaux|Parties de programme affectées|  
|---------------------|-------------------------------|  
|`LC_ALL`|Tous les comportements spécifiques aux paramètres régionaux (toutes les catégories)|  
|`LC_COLLATE`|Comportement des fonctions `strcoll` et `strxfrm`|  
|`LC_CTYPE`|Les fonctions de gestion de caractères (sauf **isdigit**, `isxdigit`, `mbstowcs` et `mbtowc`, qui ne sont pas affectés)|  
|`LC_MAX`|Identique à `LC_TIME`|  
|`LC_MIN`|Identique à `LC_ALL`|  
|`LC_MONETARY`|Les informations de mise en forme monétaire retournées par la fonction `localeconv`|  
|`LC_NUMERIC`|Le caractère de virgule décimale pour les routines de sortie mise en forme (comme `printf`), pour les routines de conversion de données, et pour les informations de mise en forme non monétaire retournées par `localeconv`|  
|`LC_TIME`|Comportement de la fonction `strftime`|  
  
 Consultez [setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) pour obtenir un exemple.  
  
## <a name="see-also"></a>Voir aussi  
 [localeconv](../c-runtime-library/reference/localeconv.md)   
 [setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [strcoll, fonctions](../c-runtime-library/strcoll-functions.md)   
 [strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
 [strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)   
 [Constantes globales](../c-runtime-library/global-constants.md)
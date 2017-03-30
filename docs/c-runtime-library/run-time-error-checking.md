---
title: "Vérifications des erreurs d’exécution │ Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.runtime
dev_langs:
- C++
helpviewer_keywords:
- run-time error checking
- run-time errors, checking
ms.assetid: c965dd01-57ad-4a3c-b1d6-5aa04f920501
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: eb9db9ea42d50faa6e7a693c95795036e650a760
ms.lasthandoff: 03/29/2017

---
# <a name="run-time-error-checking"></a>Vérifications des erreurs d’exécution
La bibliothèque Runtime C contient les fonctions qui prennent en charge les vérifications d’erreurs d’exécution (RTC). La vérification des erreurs d’exécution vous permet de générer votre programme afin que certains types d’erreurs d’exécution soient signalés. Vous spécifiez la façon dont les erreurs sont signalées et les types d’erreurs qui doivent l’être. Pour plus d’informations, consultez [Vérifications des erreurs d’exécution](http://msdn.microsoft.com/Library/dc7b2f1e-5ff6-42e0-89b3-dc9dead83ee1).  
  
 Utilisez les fonctions suivantes pour personnaliser la façon dont votre programme effectue la vérification des erreurs d’exécution.  
  
### <a name="run-time-error-checking-functions"></a>Fonctions de vérification des erreurs d’exécution  
  
|Fonction|Utilisation|  
|--------------|---------|  
|[_RTC_GetErrDesc](../c-runtime-library/reference/rtc-geterrdesc.md)|Retourne une brève description d’un type de vérification des erreurs d’exécution.|  
|[_RTC_NumErrors](../c-runtime-library/reference/rtc-numerrors.md)|Retourne le nombre total d’erreurs pouvant être détectées par les vérifications d’erreurs d’exécution.|  
|[_RTC_SetErrorFunc](../c-runtime-library/reference/rtc-seterrorfunc.md)|Désigne une fonction comme gestionnaire de rapport pour les vérifications d’erreurs d’exécution.|  
|[_RTC_SetErrorType](../c-runtime-library/reference/rtc-seterrortype.md)|Associe une erreur détectée par les vérifications d’erreurs d’exécution à un type.|  
  
## <a name="see-also"></a>Voir aussi  
 [Routines runtime par catégorie](../c-runtime-library/run-time-routines-by-category.md)   
 [/RTC (Vérifications des erreurs d’exécution)](../build/reference/rtc-run-time-error-checks.md)   
 [runtime_checks](../preprocessor/runtime-checks.md)   
 [Exemple RTC](http://msdn.microsoft.com/en-us/b3415b09-f6fd-43dc-8c02-9a910bc2574e)   
 [Routines de débogage](../c-runtime-library/debug-routines.md)

---
title: "Vérifications des erreurs d’exécution │ Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 3c1955bece0c8cdadb4a151ee06fa006402666a4
ms.openlocfilehash: 3aa56b70b02500998665289e69480570cfa39166
ms.contentlocale: fr-fr
ms.lasthandoff: 06/08/2017

---
# <a name="run-time-error-checking"></a>Vérifications des erreurs d’exécution
La bibliothèque Runtime C contient les fonctions qui prennent en charge les vérifications d’erreurs d’exécution (RTC). La vérification des erreurs d’exécution vous permet de générer votre programme afin que certains types d’erreurs d’exécution soient signalés. Vous spécifiez la façon dont les erreurs sont signalées et les types d’erreurs qui doivent l’être. Pour plus d’informations, consultez [Comment : utiliser les contrôles natifs à l'exécution](/visualstudio/debugger/how-to-use-native-run-time-checks).  
  
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
 [Routines de débogage](../c-runtime-library/debug-routines.md)
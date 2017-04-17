---
title: "Validation de paramètre | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- parameters, validation
ms.assetid: 019dd5f0-dc61-4d2e-b4e9-b66409ddf1f2
caps.latest.revision: 9
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
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 749e734bc4657efff3f0dfaeb735a0ea69375d02
ms.lasthandoff: 02/24/2017

---
# <a name="parameter-validation"></a>Validation de paramètre
La plupart des fonctions CRT avec sécurité avancée et de nombreuses fonctions préexistantes valident leurs paramètres. Elles peuvent notamment rechercher les pointeurs de valeur NULL, vérifier que les entiers se trouvent dans une plage valide ou encore vérifier que les valeurs d’énumération sont valides. Quand un paramètre non valide est trouvé, son gestionnaire s’exécute.  
  
## <a name="invalid-parameter-handler-routine"></a>Routine du gestionnaire du paramètre non valide  
 Quand une fonction de la bibliothèque Runtime C détecte un paramètre non valide, elle capture des informations sur l’erreur, puis appelle une macro qui inclut une fonction de distribution du gestionnaire du paramètre non valide, du type [_invalid_parameter](../c-runtime-library/reference/invalid-parameter-functions.md), [_invalid_parameter_noinfo](../c-runtime-library/reference/invalid-parameter-functions.md) ou [_invalid_parameter_noinfo_noreturn](../c-runtime-library/reference/invalid-parameter-functions.md). La fonction de distribution appelée varie selon que votre code est, respectivement, une version Debug, une version commerciale ou que l’erreur est n’est pas considérée comme récupérable. 
 
 Dans les versions Debug, la macro du paramètre non valide génère généralement un échec d’assertion et un point d’arrêt du débogueur est appelé avant la fonction de distribution. Quand le code est exécuté, l’assertion peut être signalée à l’utilisateur dans une boîte de dialogue contenant une option « Annuler », « Réessayer » et « Continuer » ou des choix similaires, selon le système d’exploitation et la version de la bibliothèque Runtime. Ces options permettent à l’utilisateur d’arrêter immédiatement le programme, d’attacher un débogueur ou de laisser le code existant continuer de s’exécuter, ce qui appelle la fonction de distribution. 
 
 La fonction de distribution du gestionnaire du paramètre non valide appelle à son tour le gestionnaire du paramètre non valide actuellement affecté. Par défaut, le paramètre non valide appelle `_invoke_watson` qui entraîne le blocage de l’application, autrement dit, son arrêt et la génération d’un minidump. Si le système d’exploitation le permet, une boîte de dialogue invite l’utilisateur à indiquer s’il veut charger le vidage sur incident à destination de Microsoft à des fins d’analyse.   
  
 Vous pouvez modifier ce comportement à l’aide des fonctions [_set_invalid_parameter_handler](../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md) ou [_set_thread_local_invalid_parameter_handler](../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md) pour définir le gestionnaire du paramètre non valide sur votre propre fonction. Si la fonction que vous spécifiez n’arrête pas l’application, le contrôle est retourné à la fonction qui a reçu les paramètres non valides. Dans la bibliothèque CRT, ces fonctions arrêtent normalement l’exécution de la fonction, définissent `errno` sur un code d’erreur et retournent un code d’erreur. Dans de nombreux cas, la valeur `errno` et la valeur de retour correspondent toutes les deux à `EINVAL`, ce qui indique un paramètre non valide. Dans certains cas, un code d’erreur plus spécifique est retourné, tel que `EBADF` pour un pointeur de fichier incorrect passé en tant que paramètre. Pour plus d’informations sur `errno`, consultez [errno, _doserrno, _sys_errlist et _sys_nerr](../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Fonctionnalités de sécurité dans la bibliothèque CRT](../c-runtime-library/security-features-in-the-crt.md)   
 [Fonctionnalités de la bibliothèque CRT](../c-runtime-library/crt-library-features.md)
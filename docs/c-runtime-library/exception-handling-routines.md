---
title: "Routines de gestion des exceptions │ Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.exceptions
dev_langs:
- C++
helpviewer_keywords:
- exception handling, routines
ms.assetid: f60548c6-850a-4e1e-a79b-a2a6a541ab62
caps.latest.revision: 8
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
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 3dd5d8dd77f2b62a6b0ea52e7d056b3d779cd2f4
ms.contentlocale: fr-fr
ms.lasthandoff: 03/29/2017

---
# <a name="exception-handling-routines"></a>Routines de la gestion des exceptions
Utilisez les fonctions de gestion des exceptions C++ pour la récupération après des événements inattendus pendant l’exécution du programme.  
  
### <a name="exception-handling-functions"></a>Fonctions de gestion des exceptions  
  
|Fonction|Utilisation|  
|--------------|---------|  
|[_set_se_translator](../c-runtime-library/reference/set-se-translator.md)|Gérer les exceptions Win32 (exceptions structurées en C) comme des exceptions typées C++|  
|[set_terminate](../c-runtime-library/reference/set-terminate-crt.md)|Installer votre propre routine d’arrêt que doit appeler `terminate`|  
|[set_unexpected](../c-runtime-library/reference/set-unexpected-crt.md)|Installer votre propre fonction d’arrêt que doit appeler `unexpected`|  
|[terminate](../c-runtime-library/reference/terminate-crt.md)|Appelé automatiquement dans certaines circonstances une fois que l’exception est levée. La fonction `terminate` appelle `abort` ou une fonction que vous spécifiez à l’aide de `set_terminate`|  
|[unexpected](../c-runtime-library/reference/unexpected-crt.md)|Appelle `terminate` ou une fonction que vous spécifiez à l’aide de `set_unexpected`. La fonction `unexpected` n’est pas utilisée dans l’implémentation actuelle de gestion des exceptions C++|  
  
## <a name="see-also"></a>Voir aussi  
 [Routines runtime par catégorie](../c-runtime-library/run-time-routines-by-category.md)

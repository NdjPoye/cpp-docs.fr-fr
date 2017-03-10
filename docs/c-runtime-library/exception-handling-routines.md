---
title: "Routines de gestion des exceptions │ Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: fe4946a8d3785c6295cb7537de0a11e06cd7a1cc
ms.lasthandoff: 02/24/2017

---
# <a name="exception-handling-routines"></a>Routines de la gestion des exceptions
Utilisez les fonctions de gestion des exceptions C++ pour la récupération après des événements inattendus pendant l’exécution du programme.  
  
### <a name="exception-handling-functions"></a>Fonctions de gestion des exceptions  
  
|Fonction|Utilisation|Équivalent .NET Framework|  
|--------------|---------|-------------------------------|  
|[_set_se_translator](../c-runtime-library/reference/set-se-translator.md)|Gérer les exceptions Win32 (exceptions structurées en C) comme des exceptions typées C++|Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[set_terminate](../c-runtime-library/reference/set-terminate-crt.md)|Installer votre propre routine d’arrêt que doit appeler `terminate`|Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[set_unexpected](../c-runtime-library/reference/set-unexpected-crt.md)|Installer votre propre fonction d’arrêt que doit appeler `unexpected`|Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[terminate](../c-runtime-library/reference/terminate-crt.md)|Appelé automatiquement dans certaines circonstances une fois que l’exception est levée. La fonction `terminate` appelle `abort` ou une fonction que vous spécifiez à l’aide de `set_terminate`|Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[unexpected](../c-runtime-library/reference/unexpected-crt.md)|Appelle `terminate` ou une fonction que vous spécifiez à l’aide de `set_unexpected`. La fonction `unexpected` n’est pas utilisée dans l’implémentation actuelle de gestion des exceptions C++|[System::Exception, classe](https://msdn.microsoft.com/en-us/library/system.exception.aspx)|  
  
## <a name="see-also"></a>Voir aussi  
 [Routines runtime par catégorie](../c-runtime-library/run-time-routines-by-category.md)

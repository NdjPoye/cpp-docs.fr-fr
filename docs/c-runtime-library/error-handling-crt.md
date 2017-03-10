---
title: Gestion des erreurs (CRT) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.errors
dev_langs:
- C++
helpviewer_keywords:
- error handling, C routines for
- logic errors
- error handling, library routines
- testing, for program errors
ms.assetid: 125ac697-9eb0-4152-a440-b7842f23d97f
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
ms.openlocfilehash: ab0f6998aa2f4f6ba5066cbc1d4c6813dcbaab0b
ms.lasthandoff: 02/24/2017

---
# <a name="error-handling-crt"></a>Gestion des erreurs (CRT)
Utilisez ces routines pour gérer les erreurs de programme.  
  
### <a name="error-handling-routines"></a>Routines de gestion des erreurs  
  
|Routine|Utilisation|Équivalent .NET Framework|  
|-------------|---------|-------------------------------|  
|[assert](../c-runtime-library/reference/assert-macro-assert-wassert.md), macro|Vérifie les erreurs logiques de programmation ; disponible dans les versions Release et Debug de la bibliothèque Runtime|[System::Diagnostics::Debug::Assert](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.assert.aspx)|  
|[_ASSERT, _ASSERTE](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md), macros|Similaire à `assert`, mais uniquement disponible dans les versions Debug de la bibliothèque Runtime|[System::Diagnostics::Debug::Assert](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.assert.aspx)|  
|[clearerr](../c-runtime-library/reference/clearerr.md)|Réinitialiser l’indicateur d’erreur. L’appel de `rewind` ou la fermeture d’un flux réinitialise également l’indicateur d’erreur.|Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[_eof](../c-runtime-library/reference/eof.md)|Vérifier la fin du fichier dans les E/S de bas niveau|Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[feof](../c-runtime-library/reference/feof.md)|Vérifier la fin du fichier. La fin du fichier est également indiquée quand `_read` retourne la valeur 0.|Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[ferror](../c-runtime-library/reference/ferror.md)|Vérifier les erreurs d’E/S du flux|Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[_RPT, _RPTF](../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md), macros|Générer un rapport similaire à `printf`, mais uniquement disponible dans les versions Debug de la bibliothèque Runtime|Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).|  
|[_set_error_mode](../c-runtime-library/reference/set-error-mode.md)|Modifie `__error_mode` pour déterminer un emplacement autre que celui utilisé par défaut dans lequel le Runtime C écrit un message d’erreur pour une erreur qui risque de mettre fin au programme.||  
|[_set_purecall_handler](../c-runtime-library/reference/get-purecall-handler-set-purecall-handler.md)|Définit le gestionnaire pour un appel de fonction virtuelle pure.||  
  
## <a name="see-also"></a>Voir aussi  
 [Routines runtime par catégorie](../c-runtime-library/run-time-routines-by-category.md)

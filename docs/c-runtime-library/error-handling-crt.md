---
title: Gestion des erreurs (CRT) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: c.errors
dev_langs: C++
helpviewer_keywords:
- error handling, C routines for
- logic errors
- error handling, library routines
- testing, for program errors
ms.assetid: 125ac697-9eb0-4152-a440-b7842f23d97f
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f40b2deb5c78667e5343bd2be0948252e2f2e154
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="error-handling-crt"></a>Gestion des erreurs (CRT)
Utilisez ces routines pour gérer les erreurs de programme.  
  
### <a name="error-handling-routines"></a>Routines de gestion des erreurs  
  
|Routine|Utilisez|  
|-------------|---------|  
|[assert](../c-runtime-library/reference/assert-macro-assert-wassert.md), macro|Vérifier les erreurs logiques de programmation ; disponible dans les versions Release et Debug de la bibliothèque runtime.|  
|[_ASSERT, _ASSERTE](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md), macros|Similaire à `assert`, mais uniquement disponible dans les versions Debug de la bibliothèque runtime.|  
|[clearerr](../c-runtime-library/reference/clearerr.md)|Réinitialiser l’indicateur d’erreur. L’appel de `rewind` ou la fermeture d’un flux réinitialise également l’indicateur d’erreur.|  
|[_eof](../c-runtime-library/reference/eof.md)|Vérifier la fin du fichier dans les E/S de bas niveau.|  
|[feof](../c-runtime-library/reference/feof.md)|Vérifier la fin du fichier. La fin du fichier est également indiquée quand `_read` retourne la valeur 0.|  
|[ferror](../c-runtime-library/reference/ferror.md)|Vérifier les erreurs d’E/S du flux.|  
|[_RPT, _RPTF](../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md), macros|Générer un rapport similaire à `printf`, mais uniquement disponible dans les versions Debug de la bibliothèque runtime.|  
|[_set_error_mode](../c-runtime-library/reference/set-error-mode.md)|Modifie `__error_mode` pour déterminer un emplacement autre que celui utilisé par défaut dans lequel le Runtime C écrit un message d’erreur pour une erreur qui risque de mettre fin au programme.|  
|[_set_purecall_handler](../c-runtime-library/reference/get-purecall-handler-set-purecall-handler.md)|Définit le gestionnaire pour un appel de fonction virtuelle pure.|  
  
## <a name="see-also"></a>Voir aussi  
 [Routines runtime par catégorie](../c-runtime-library/run-time-routines-by-category.md)
---
title: "Gestion des erreurs (CRT) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.errors"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "gestion des erreurs, routines C pour"
  - "gestion des erreurs, routines de bibliothèque"
  - "erreurs de logique"
  - "tester, les erreurs de programmation"
ms.assetid: 125ac697-9eb0-4152-a440-b7842f23d97f
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Gestion des erreurs (CRT)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Utilisez ces routines pour gérer des erreurs de programme.  
  
### Routines de gestion des erreurs  
  
|Routine|Utilisez|Équivalent de .NET Framework|  
|-------------|--------------|----------------------------------|  
|[assert](../c-runtime-library/reference/assert-macro-assert-wassert.md) macro|Test des erreurs de logique de programmation ; disponible dans la version et les versions de débogage de la bibliothèque d'exécutables|[\<caps:sentence id\="tgt8" sentenceid\="14fd9bf776829d73028df00162f7533f" class\="tgtSentence"\>System::Diagnostics::Debug::Assert\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.assert.aspx)|  
|macros [\_ASSERT, \_ASSERTE](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)|Similaire à `assert`, mais uniquement disponible dans les versions de débogage des bibliothèques Runtime|[\<caps:sentence id\="tgt11" sentenceid\="14fd9bf776829d73028df00162f7533f" class\="tgtSentence"\>System::Diagnostics::Debug::Assert\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.assert.aspx)|  
|[clearerr](../c-runtime-library/reference/clearerr.md)|Réinitialisez l'indicateur d'erreurs.  Appel `rewind` ou la fermeture un flux de données rétablit également l'indicateur d'erreur.|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_eof](../c-runtime-library/reference/eof.md)|Contrôle de file close dans l'E\/S de bas niveau|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[feof](../c-runtime-library/reference/feof.md)|Test pour la fin de fichier  Fin de fichier est également indiquée lors retourne 0 pour `_read` .|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[ferror](../c-runtime-library/reference/ferror.md)|Test des erreurs d'E\/S de flux de données|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_RPT, \_RPTF](../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md) macros|Génère un rapport similaire à `printf`, mais uniquement disponible dans les versions de débogage de la bibliothèque d'exécutables|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_set\_error\_mode](../c-runtime-library/reference/set-error-mode.md)|Modifie `__error_mode` pour déterminer un emplacement non défini par défaut dans lequel le run\-time C écrit un message d'erreur pour une erreur qui peut terminer le programme.||  
|[\_set\_purecall\_handler](../c-runtime-library/reference/get-purecall-handler-set-purecall-handler.md)|Définit le gestionnaire d'un appel de fonction virtuelle pure.||  
  
## Voir aussi  
 [Routines runtime par catégorie](../c-runtime-library/run-time-routines-by-category.md)
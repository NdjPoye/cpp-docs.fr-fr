---
title: "Erreur irrécupérable C1189 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1189
dev_langs:
- C++
helpviewer_keywords:
- C1189
ms.assetid: 2e5c8a78-edd4-411c-b619-558a96be148a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2330d49f817012fc2e0381a0991f709ada74ea32
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1189"></a>Erreur irrécupérable C1189
\#Erreur : message d’erreur fourni par l’utilisateur  
  
 L’erreur C1189 est générée par le `#error` la directive. Le développeur qui code la directive spécifie le texte du message d’erreur. Pour plus d’informations, consultez [#error Directive (C/C++)](../../preprocessor/hash-error-directive-c-cpp.md).  
  
 L’exemple suivant génère l’erreur C1189. Dans l’exemple, le développeur émet un message d’erreur personnalisé, car le `_WIN32` identificateur n’est pas défini :  
  
```  
// C1189.cpp  
#undef _WIN32  
#if !defined(_WIN32)  
#error _WIN32 must be defined   // C1189  
#endif  
```  
  
 Vous pouvez également voir cette erreur si vous générez un projet ATL à l’aide de la **/ robust** option du compilateur MIDL. Utilisez le **/ robust** commutateur à générer uniquement [!INCLUDE[win2kfamily](../../c-runtime-library/includes/win2kfamily_md.md)] et versions ultérieures de Windows. Pour corriger cette erreur, utilisez une des procédures suivantes :  
  
-   Modifiez cette ligne dans le fichier dlldatax.c :  
  
```  
#define _WIN32_WINNT 0x0400   // for WinNT 4.0 or Windows 95 with DCOM  
```  
  
 à :  
  
```  
#define _WIN32_WINNT 0x0500   // for WinNT 4.0 or Windows 95 with DCOM  
```  
  
-   Utilisez le **avancé** page de propriétés dans le **MIDL** dossier de page de propriété à supprimer le **/ robust** basculer, puis spécifiez le **/no_robust** commutateur non valide. Pour plus d’informations, consultez [Pages de propriétés MIDL : avancé](../../ide/midl-property-pages-advanced.md).  
  
## <a name="see-also"></a>Voir aussi  
 [#define, directive (C/C++)](../../preprocessor/hash-define-directive-c-cpp.md)
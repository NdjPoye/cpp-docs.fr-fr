---
title: "Routines de la gestion d&#39;exceptions | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.exceptions"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "gestion des exceptions, routines"
ms.assetid: f60548c6-850a-4e1e-a79b-a2a6a541ab62
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Routines de la gestion d&#39;exceptions
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Utilisez les fonctions de gestion des exceptions C\+\+ pour extraire des événements inattendus lors de l'exécution du programme.  
  
### Fonctions de gestion des exceptions  
  
|Fonction|Utilisez|Équivalent de .NET Framework|  
|--------------|--------------|----------------------------------|  
|[\_set\_se\_translator](../c-runtime-library/reference/set-se-translator.md)|Gère les exceptions Win32 \(exceptions structurées C\) comme des exceptions de type C\+\+.|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[set\_terminate](../c-runtime-library/reference/set-terminate-crt.md)|Installez votre propre routine d'arrêt pour être appelé par `terminate`|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[set\_unexpected](../c-runtime-library/reference/set-unexpected-crt.md)|Installez votre propre fonction d'arrêt pour qu'elle soit appelée par `unexpected`.|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[terminate](../c-runtime-library/reference/terminate-crt.md)|Appelé automatiquement dans certains cas aprés qu'une exception soit levée.  La fonction `terminate` appelle `abort` ou une fonction que vous spécifiez en utilisant `set_terminate`|Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).|  
|[inattendu](../c-runtime-library/reference/unexpected-crt.md)|Appelle `terminate` ou une fonction que vous spécifiez en utilisant `set_unexpected`.  La fonction `unexpected` n'est pas utilisé dans l'implémentation actuelle de gestion des exceptions Microsoft C\+\+|[\<caps:sentence id\="tgt30" sentenceid\="ec8332f3bf55c7bd183338eca87744ec" class\="tgtSentence"\>System::Exception Class.\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.exception.aspx)|  
  
## Voir aussi  
 [Routines runtime par catégorie](../c-runtime-library/run-time-routines-by-category.md)
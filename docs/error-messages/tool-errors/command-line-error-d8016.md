---
title: "Erreur de ligne de commande&#160;D8016 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "D8016"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "D8016"
ms.assetid: eec51312-7471-4f92-94b2-d517cafc8ef5
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Erreur de ligne de commande&#160;D8016
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

options de ligne de commande 'option1' et 'option2' non compatibles  
  
 Les options de ligne de commande ne peuvent pas être spécifiées simultanément.  
  
 Vérifiez les options spécifiées pour les variables d'environnement, telles que CL.  
  
 **\/clr** implique **\/EHa** et vous ne pouvez pas spécifier d'autre option du compilateur **\/EH** avec **\/clr**.  Pour plus d'informations, consultez [\/clr \(Compilation pour le Common Language Runtime\)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
 L'erreur D8016 peut être générée après la mise à jour d'un projet [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] 6.0 : le processus de l'Assistant Mise à jour de projet peut activer **\/RTC** pour chaque fichier de code source contenu dans le projet, ce qui substitue le paramètre **\/RTC** du projet.  Pour remédier à cela, remplacez le paramètre **\/RTC** pour chaque fichier de code source dans le projet par le paramètre par défaut, ce qui signifie que le paramètre du projet pour **\/RTC** sera appliqué à chaque fichier.  
  
 Consultez [\/RTC \(Vérifications des erreurs au moment de l'exécution\)](../../build/reference/rtc-run-time-error-checks.md) pour plus d'informations sur la modification de la valeur de la propriété **\/RTC**.
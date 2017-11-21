---
title: Erreur de ligne de commande D8016 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: D8016
dev_langs: C++
helpviewer_keywords: D8016
ms.assetid: eec51312-7471-4f92-94b2-d517cafc8ef5
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: dccba5491919c2a5623f7c566a88c1388746e49e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="command-line-error-d8016"></a>Erreur de ligne de commande D8016
les options de ligne de commande 'option1' et 'option2' sont incompatibles  
  
 Les options de ligne de commande ne peut pas être spécifiées ensemble.  
  
 Vérifiez les variables d’environnement, telles que CL, pour les spécifications de l’option.  
  
 **/ CLR** implique **/EHa**, et vous ne pouvez pas spécifier n’importe quel autre **/EH** option du compilateur avec **/CLR**. Pour plus d’informations, consultez l’article [/clr (Compilation pour le Common Language Runtime)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
 Vous risquez d’obtenir D8016 après la mise à jour un [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] projet 6.0 : le processus d’Assistant de mise à jour de projet peut activer **/RTC** pour chaque fichier de code source dans le projet, ce qui substitue le **/RTC** définition pour le projet.  Pour résoudre, modifiez le **/RTC.** définition pour chaque fichier de code source dans le projet pour le paramètre par défaut, ce qui signifie que le paramètre du projet pour **/RTC** sera appliquée pour chaque fichier.  
  
 Consultez [/RTC (vérifications des erreurs Run-Time)](../../build/reference/rtc-run-time-error-checks.md) pour plus d’informations sur la modification de la **/RTC.** définition de la propriété.
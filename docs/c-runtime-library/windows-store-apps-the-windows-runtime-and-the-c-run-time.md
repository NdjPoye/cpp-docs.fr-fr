---
title: Applications du Windows Store, Windows Runtime et Runtime C | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 356d6d8d-76ee-4181-9ad0-6f24b2fede38
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 0eb057f9d229c659f339f996d1ff38f65fd2e018
ms.openlocfilehash: fc0ed4b45e04357fae46fb1391d55d184440f12d
ms.contentlocale: fr-fr
ms.lasthandoff: 06/01/2017

---
# <a name="windows-store-apps-the-windows-runtime-and-the-c-run-time"></a>Applications Windows Store, Windows Runtime et exécution C
Les applications du [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] sont des programmes qui s'exécutent dans Windows Runtime, qui s'exécute lui-même sur [!INCLUDE[win8](../build/reference/includes/win8_md.md)].  Windows Runtime est un environnement fiable qui contrôle les fonctions, les variables et les ressources auxquelles une application [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] a accès. Cependant, par sa conception, Windows Runtime présente des restrictions qui empêchent l’utilisation de la plupart des fonctionnalités des bibliothèques Runtime C (CRT) dans les applications du [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)].  
  
 Windows Runtime ne prend pas en charge les fonctionnalités CRT suivantes :  
  
-   La plupart des fonctions CRT liées à une fonctionnalité non prise en charge.  
  
     Par exemple, une application du [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] ne peut pas créer un processus en utilisant les familles de routines `exec` et `spawn`.  
  
     Quand une fonction CRT n'est pas prise en charge dans une application du [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)], ce fait est noté dans son article de référence.  
  
-   La plupart des fonctions de chaînes et de caractères multioctets.  
  
     Cependant, le texte Unicode et ANSI est pris en charge.  
  
-   Applications de console et arguments de ligne de commande.  
  
     Toutefois, les applications de bureau traditionnelles prennent toujours en charge la console et les arguments de ligne de commande.  
  
-   Variables d'environnement.  
  
-   Le concept de répertoire de travail actif.  
  
-   Applications du [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] et DLL statiquement liées au CRT et générées à l'aide des options de compilateur [/MT](../build/reference/md-mt-ld-use-run-time-library.md) ou `/MTd`.  
  
     Autrement dit, une application qui utilise une version statique multithread du CRT.  
  
-   Application générée à l'aide de l'option de compilateur [/MDd](../build/reference/md-mt-ld-use-run-time-library.md).  
  
     Autrement dit, une version de débogage multithread propre à une DLL du CRT. Une telle application n'est pas prise en charge dans le [!INCLUDE[win8_appstore_long](../build/reference/includes/win8_appstore_long_md.md)].  
  
 Pour obtenir la liste complète des fonctions CRT non accessibles à une application du [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)], ainsi que des suggestions de fonctions alternatives, consultez [Fonctions CRT non prises en charge avec /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="see-also"></a>Voir aussi  
 [Compatibilité ](../c-runtime-library/compatibility.md)   
 [Fonctions CRT non prises en charge par Windows Runtime](../c-runtime-library/windows-runtime-unsupported-crt-functions.md)   
 [Routines runtime par catégorie](../c-runtime-library/run-time-routines-by-category.md)

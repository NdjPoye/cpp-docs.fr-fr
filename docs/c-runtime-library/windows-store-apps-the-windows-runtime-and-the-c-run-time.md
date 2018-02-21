---
title: Applications UWP, Windows Runtime et Runtime C | Microsoft Docs
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 120e02caab735455224ad75f0944ceb25f4baf33
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="uwp-apps-the-windows-runtime-and-the-c-run-time"></a>Applications UWP, Windows Runtime et Runtime C

Les applications de plateforme Windows universelle (UWP) sont des programmes qui s’exécutent dans Windows Runtime sur [!INCLUDE[win8](../build/reference/includes/win8_md.md)]. Windows Runtime est un environnement fiable qui contrôle les fonctions, les variables et les ressources disponibles pour une application UWP. Cependant, par sa conception, Windows Runtime présente des restrictions qui empêchent l’utilisation de la plupart des fonctionnalités des bibliothèques Runtime C (CRT) dans les applications UWP.

Windows Runtime ne prend pas en charge les fonctionnalités CRT suivantes :

- La plupart des fonctions CRT liées à une fonctionnalité non prise en charge.

   Par exemple, une application UWP ne peut pas créer un processus en utilisant les familles de routines `exec` et `spawn`.

   Quand une fonction CRT n’est pas prise en charge dans une application UWP, son article de référence le mentionne.

- La plupart des fonctions de chaînes et de caractères multioctets.

   Cependant, le texte Unicode et ANSI est pris en charge.

- Applications de console et arguments de ligne de commande.

   Toutefois, les applications de bureau traditionnelles prennent toujours en charge la console et les arguments de ligne de commande.

- Variables d'environnement.

- Le concept de répertoire de travail actif.

- Applications UWP et DLL statiquement liées au CRT et générées à l'aide des options de compilateur [/MT](../build/reference/md-mt-ld-use-run-time-library.md) ou `/MTd`.

   Autrement dit, une application qui utilise une version statique multithread du CRT.

- Application générée à l'aide de l'option de compilateur [/MDd](../build/reference/md-mt-ld-use-run-time-library.md).

   Autrement dit, une version de débogage multithread propre à une DLL du CRT. Une telle application n'est pas prise en charge dans Windows Runtime.

Pour obtenir la liste complète des fonctions CRT non disponibles pour une application UWP ainsi que des suggestions de fonctions alternatives, consultez [Fonctions CRT non prises en charge dans les applications de plateforme Windows universelle](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="see-also"></a>Voir aussi
 [Compatibilité](../c-runtime-library/compatibility.md) [Fonctions CRT non prises en charge par Windows Runtime](../c-runtime-library/windows-runtime-unsupported-crt-functions.md) [Routines runtime par catégorie](../c-runtime-library/run-time-routines-by-category.md)
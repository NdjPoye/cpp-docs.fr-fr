---
title: "Liaison d’importations | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- /DELAY:NOBIND linker option
- DELAY:NOBIND linker option
ms.assetid: bb766038-deb1-41b1-bcbc-29a30e8c1e2a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4f462eeea9f2bca566745d425b84bd1506f52fc8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="binding-imports"></a>Liaison d’importations
Le comportement de l’éditeur de liens par défaut est pour créer une table d’adresses importation pouvant être liées pour la DLL à chargement différé. Si la DLL est liée, la fonction d’assistance tente d’utiliser les informations liées au lieu d’appeler **GetProcAddress** sur chaque importation référencée. Si l’horodatage ou l’adresse préférée ne correspondre pas celles de la DLL chargée, la fonction d’assistance suppose la table d’adresses importation liée est obsolète et se poursuit comme s’il n’existe pas.  
  
 Si vous n’envisagez pas de lier les importations à chargement différé de DLL, en spécifiant [/Delay](../../build/reference/delay-delay-load-import-settings.md): nobind sur la ligne de commande de l’éditeur de liens empêche la table d’adresses importation liées généré et beaucoup d’espace dans le fichier image.  
  
## <a name="see-also"></a>Voir aussi  
 [Prise en charge de l’éditeur de liens pour les DLL à chargement différé](../../build/reference/linker-support-for-delay-loaded-dlls.md)
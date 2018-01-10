---
title: "Erreur irrécupérable C1510 | Documents Microsoft"
ms.custom: 
ms.date: 04/11/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1510
dev_langs: C++
helpviewer_keywords: C1510
ms.assetid: 150c827f-9514-41a9-8d7e-82f820749bcb
caps.latest.revision: "1"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8d4128580facdc87239d0087fef1cf9eff701854
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1510"></a>Erreur irrécupérable C1510
Impossible d'ouvrir la ressource de langage clui.dll  
  
 Le compilateur ne peut pas charger la DLL de ressource de langue.  
  
Il existe deux raisons courantes pour résoudre ce problème. Lorsque vous utilisez le compilateur 32 bits et les outils, vous pouvez voir cette erreur pour les grands projets qui utilisent plus de 2 Go de mémoire au cours d’un lien. Une solution possible sur les systèmes 64 bits de Windows consiste à utiliser natif 64 bits ou croisée de compilateur et les outils de génération de votre code. Utilise le plus grand espace de mémoire disponible pour les applications 64 bits. Si vous devez utiliser un compilateur 32 bits, car il est en cours d’exécution sur un système 32 bits, dans certains cas, vous pouvez augmenter la quantité de mémoire disponible pour l’éditeur de liens à 3 Go. Pour plus d’informations, consultez [4-Gigabyte Tuning : BCDEdit et Boot.ini](https://msdn.microsoft.com/library/vs/alm/bb613473(v=vs.85).aspx) et [BCDEdit /Set increaseuserva](https://msdn.microsoft.com/library/ff542202.aspx) commande.  

Les autres causes est une installation de Visual Studio incorrectes ou incomplète. Dans ce cas, exécutez le programme d’installation pour réparer ou réinstaller Visual Studio.  
  
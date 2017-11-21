---
title: Erreur BSCMAKE BK1506 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: BK1506
dev_langs: C++
helpviewer_keywords: BK1506
ms.assetid: f51f8cea-f8fc-4323-bcf2-b7bd119792ee
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c792f28b29ca9abf8594fbe6e351c4782b149a61
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="bscmake-error-bk1506"></a>Erreur BSCMAKE BK1506
Impossible d’ouvrir le fichier 'nom_fichier' [ : raison]  
  
 BSCMAKE ne peut pas ouvrir le fichier.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Pour corriger en vérifiant les causes possibles suivantes  
  
1.  Fichier est verrouillé par un autre processus. Si `reason` indique que **autorisation refusée**, le navigateur peut être à l’aide du fichier. Fermez la fenêtre de navigation et recommencez la génération.  
  
2.  Un disque saturé.  
  
3.  Une erreur matérielle.  
  
4.  Le fichier de sortie spécifié a le même nom qu’un sous-répertoire existant.
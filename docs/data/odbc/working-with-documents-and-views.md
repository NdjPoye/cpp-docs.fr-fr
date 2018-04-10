---
title: Utilisation des Documents et vues | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], documents
- MFC [C++], views
- views [C++], MFC
- documents [C++], MFC
ms.assetid: 349b142d-1c5a-4b99-9de4-241e41d3d2f1
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5558e106ead5b56e982c6280fecc8a8418b3ebc6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="working-with-documents-and-views"></a>Utilisation des documents et vues
La bibliothèque Microsoft Foundation Classes (MFC) s’appuie sur l’architecture document/vue pour la plupart de ses fonctionnalités. En règle générale, un document stocke vos données et une vue affiche dans la zone cliente d’une fenêtre frame et gère l’interaction avec les données de l’utilisateur. La vue communique avec le document pour obtenir et mettre à jour les données. Vous pouvez utiliser les classes de base de données avec l’infrastructure ou sans lui.  
  
 Pour plus d’informations sur l’utilisation des classes de base de données dans le framework, consultez [MFC : utilisation de Classes de base de données avec des Documents et vues](../../data/mfc-using-database-classes-with-documents-and-views.md).  
  
 Par défaut, l’Assistant Application MFC crée une application squelette sans prise en charge de la base de données. Toutefois, vous pouvez sélectionner des options permettant d’inclure la prise en charge minimale de la base de données ou prise en charge basée sur formulaire plus complète. Pour plus d’informations sur les options de l’Assistant application, consultez [prise en charge de la base de données, Assistant Application MFC](../../mfc/reference/database-support-mfc-application-wizard.md).  
  
 Vous pouvez également utiliser les classes de base de données sans utiliser l’architecture document/vue complète. Pour plus d’informations, consultez [MFC : à l’aide de Classes de base de données sans document ni vue](../../data/mfc-using-database-classes-without-documents-and-views.md).  
  
## <a name="see-also"></a>Voir aussi  
 [ODBC et MFC](../../data/odbc/odbc-and-mfc.md)
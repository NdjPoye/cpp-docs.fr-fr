---
title: Prise en charge COM + 1.0 dans les projets ATL | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: vc.appwiz.ATL.MTS
dev_langs: C++
helpviewer_keywords: ATL projects, COM+ 1.0 support
ms.assetid: 51fb08ac-d632-4657-a4e0-d3f989f0b6f8
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a3b55cb078dc5db1f0bf727a10f2a77ebfddd260
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="com-10-support-in-atl-projects"></a>Prise en charge COM + 1.0 dans les projets ATL
Vous pouvez utiliser la [Assistant Projet ATL](../../atl/reference/creating-an-atl-project.md) pour créer un projet avec prise en charge de base des composants COM + 1.0.  
  
 COM + 1.0 est conçu pour le développement d’applications distribuées dans un composant. Il fournit également une infrastructure runtime pour le déploiement et la gestion de ces applications.  
  
 Si vous sélectionnez le **prise en charge COM + 1.0** case à cocher, l’Assistant modifie le script de compilation dans l’étape de liaison. Plus précisément, les COM + 1.0 projet liens vers les bibliothèques suivantes :  
  
-   Comsvcs.lib  
  
-   Mtxguid.lib  
  
 Si vous sélectionnez le **prise en charge COM + 1.0** case à cocher, vous pouvez également sélectionner **inscription de composants de prise en charge**. L’inscription de composants permet à votre objet COM + 1.0 obtenir la liste des composants, d’inscrire des composants ou d’annuler l’inscription de composants (individuellement ou tous en même temps).  
  
## <a name="see-also"></a>Voir aussi  
 [Notions de base des objets ATL COM](../../atl/fundamentals-of-atl-com-objects.md)   
 [Programmation avec ATL et le Code d’exécution C](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [Configurations de projet ATL par défaut](../../atl/reference/default-atl-project-configurations.md)


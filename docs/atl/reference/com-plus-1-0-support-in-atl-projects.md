---
title: Prise en charge COM + 1.0 dans les projets ATL | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc.appwiz.ATL.MTS
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, COM+ 1.0 support
ms.assetid: 51fb08ac-d632-4657-a4e0-d3f989f0b6f8
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 7521c1dae6fd29b8b951d23fe33c91179d4b46ed
ms.lasthandoff: 02/24/2017

---
# <a name="com-10-support-in-atl-projects"></a>Prise en charge COM + 1.0 dans les projets ATL
Vous pouvez utiliser la [Assistant Projet ATL](../../atl/reference/creating-an-atl-project.md) pour créer un projet avec prise en charge de base des composants COM + 1.0.  
  
 COM + 1.0 est conçu pour le développement d’applications distribuées utilisant des composants. Il fournit également une infrastructure runtime pour le déploiement et la gestion de ces applications.  
  
 Si vous sélectionnez le **prise en charge COM + 1.0** case à cocher, l’Assistant modifie le script de compilation dans l’étape de liaison. Plus précisément, le COM + 1.0 projet lié aux bibliothèques suivantes :  
  
-   Comsvcs.lib  
  
-   Mtxguid.lib  
  
 Si vous sélectionnez le **prise en charge COM + 1.0** case à cocher, vous pouvez également sélectionner **inscription de composants de prise en charge**. L’inscription de composants permet à votre objet COM + 1.0 obtenir la liste des composants, d’inscrire des composants ou d’annuler l’inscription de composants (individuellement ou tous en même temps).  
  
## <a name="see-also"></a>Voir aussi  
 [Principes de base des objets ATL COM](../../atl/fundamentals-of-atl-com-objects.md)   
 [Programmation avec ATL et le Code C Run-Time](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [Configurations des projets ATL par défaut](../../atl/reference/default-atl-project-configurations.md)



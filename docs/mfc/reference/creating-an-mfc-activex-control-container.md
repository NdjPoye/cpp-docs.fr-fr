---
title: "Création d’un conteneur de contrôle ActiveX MFC | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.appwiz.activex.container
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], containers
- ActiveX control containers [MFC], creating
- containers [MFC], creating
- OLE controls [MFC], containers
ms.assetid: ec70e137-7c14-4940-bd0e-fd4edcc63ea5
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 4a770b6508067913aec51b8b3878f33e30eed4bb
ms.openlocfilehash: c9ac70acd706237cfeb40e709d2562883263c687
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="creating-an-mfc-activex-control-container"></a>Création d'un conteneur de contrôles ActiveX MFC
Un conteneur de contrôles ActiveX est un programme parent qui fournit l’environnement pour un contrôle ActiveX (anciennement appelés OLE) à exécuter. Vous pouvez créer une application capable de contenir des contrôles ActiveX avec ou sans MFC, mais il est beaucoup plus facile de faire avec MFC.  
  
 Création d’un programme MFC conteneur à l’aide du [Assistant Application MFC](../../mfc/reference/mfc-application-wizard.md) permet d’accéder aux principales fonctionnalités des contrôles ActiveX et Automation qui sont implémentées par les classes MFC et ActiveX. Ces fonctionnalités incluent la modification visuelle, l’Automation, la création de fichiers composés et prend en charge pour les contrôles. Les options d’édition visuelle Assistant Application MFC qui prennent en charge votre programme parent incluent la création d’un conteneur, un mini-serveur, un serveur complet et un programme qui est un conteneur et un serveur.  
  
-   **Nouvelle Application MFC**. Pour créer un nouveau programme MFC contenant Automation, la modification sur place, fichiers composés ou contrôle prennent en charge, utilisez l’Assistant Application MFC et choisissez les options Automation appropriées.  
  
-   **Application MFC existante**. Si vous ajoutez la relation contenant-contenu de contrôle à une application MFC existante, consultez [conteneurs de contrôles OLE : activation manuelle de la contenance de contrôles OLE](../../mfc/activex-control-containers-manually-enabling-activex-control-containment.md).  
  
### <a name="to-create-an-activex-container-for-any-of-the-following-types-of-applications"></a>Pour créer un conteneur ActiveX pour un des types suivants d’applications  
  
1.  [Conteneurs](../../mfc/containers.md)  
  
2.  [Édition visuelle](../../mfc/ole-mfc.md)  
  
3.  [Contrôles ActiveX MFC](../../mfc/mfc-activex-controls.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Types de projets Visual C++](../../ide/visual-cpp-project-types.md)



---
title: "Création d’un conteneur de contrôle ActiveX MFC | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.appwiz.activex.container
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [C++], containers
- ActiveX control containers [C++], creating
- containers [C++], creating
- OLE controls [C++], containers
ms.assetid: ec70e137-7c14-4940-bd0e-fd4edcc63ea5
caps.latest.revision: 8
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
ms.openlocfilehash: 54e2edef0a0b37da1260e9d62c57524e864356be
ms.lasthandoff: 02/24/2017

---
# <a name="creating-an-mfc-activex-control-container"></a>Création d'un conteneur de contrôles ActiveX MFC
Un conteneur de contrôles ActiveX est un programme parent qui fournit l’environnement pour un contrôle ActiveX (anciennement appelés OLE) à exécuter. Vous pouvez créer une application capable de contenir des contrôles ActiveX avec ou sans MFC, mais il est plus facile à faire avec MFC.  
  
 Création d’un programme conteneur MFC à l’aide du [Assistant Application MFC](../../mfc/reference/mfc-application-wizard.md) permet d’accéder aux principales fonctionnalités des contrôles ActiveX et Automation qui sont implémentées par les classes MFC et ActiveX. Ces fonctionnalités comprennent l’édition visuelle, l’Automation, la création de fichiers composés et prendre en charge pour les contrôles. Les options d’édition visuelle Assistant Application MFC qui prend en charge votre programme parent comprennent la création d’un conteneur, un mini-serveur, un serveur complet et un programme qui est un conteneur et un serveur.  
  
-   **Nouvelle Application MFC**. Pour créer un nouveau programme MFC contenant Automation, édition visuelle, fichiers composés ou contrôle prennent en charge, utilisez l’Assistant Application MFC et choisissez les options Automation appropriées.  
  
-   **Application MFC existante**. Si vous ajoutez la contenance de contrôles à une application MFC existante, consultez [conteneurs de contrôles OLE : activation manuelle de la contenance de contrôles OLE](../../mfc/activex-control-containers-manually-enabling-activex-control-containment.md).  
  
### <a name="to-create-an-activex-container-for-any-of-the-following-types-of-applications"></a>Pour créer un conteneur ActiveX pour tous les types suivants d’applications  
  
1.  [Conteneurs](../../mfc/containers.md)  
  
2.  [Édition visuelle](../../mfc/ole-mfc.md)  
  
3.  [Contrôles ActiveX MFC](../../mfc/mfc-activex-controls.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Types de projets Visual C++](../../ide/visual-cpp-project-types.md)



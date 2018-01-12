---
title: "MFC MBCS DLL, complément | Documents Microsoft"
ms.custom: 
ms.date: 08/20/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MBCS
- MFC
ms.assetid: bebec0ff-e019-42ca-b5df-8c218ac5b54a
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 176ed47b4d6a799cf53d2a1cea8cb232f1c2c4aa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-mbcs-dll-add-on"></a>MFC MBCS DLL, complément
 Vous avez besoin des DLL multioctets pour pouvoir générer un projet MFC dans Visual Studio 2015 dont la propriété **Jeu de caractères** est définie sur **Utiliser le jeu de caractères multioctet (MBCS)** ou **Non défini**.  

**Visual Studio 2013**: Téléchargez la DLL à [bibliothèque MFC multioctet pour Visual Studio 2013](https://www.microsoft.com/en-us/download/details.aspx?id=40770).

**Visual Studio 2015**: la DLL est incluse dans les composants de programme d’installation de Visual C++. Visual C++ et MFC sont des configurations dont l’installation est facultative dans le programme d’installation de Visual Studio. Pour que MFC soit installé, choisissez **Personnalisé** dans le programme d’installation et, sous **Langages de programmation**, assurez-vous que **Visual C++** et **Microsoft Foundation Classes pour C++** sont sélectionnés. Si vous avez déjà installé Visual Studio, il vous est demandé d’installer Visual C++ et/ou MFC quand vous tentez de créer un projet MFC.  
  
**Visual Studio 2017**: la DLL est installée avec le **développement de bureau avec C++** la charge de travail lorsque vous sélectionnez **prise en charge MFC et ATL** à partir de la **composants facultatifs** volet.

  
## <a name="see-also"></a>Voir aussi  
 [Versions de bibliothèque MFC](../mfc/mfc-library-versions.md)


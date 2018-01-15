---
title: "MFC MBCS DLL, complément | Documents Microsoft"
ms.custom: 
ms.date: 1/04/2018
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MBCS
- MFC
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d6f134110ff95956cc37d6e038a680ff27cbc298
ms.sourcegitcommit: 56f6fce7d80e4f61d45752f4c8512e4ef0453e58
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2018
---
# <a name="mfc-mbcs-dll-add-on"></a>MFC MBCS DLL, complément

Prise en charge des MFC et bibliothèques ensemble (MBCS) caractère multioctet nécessite une étape supplémentaire lors de l’installation de Visual Studio dans Visual Studio 2013, 2015 et 2017.

**Visual Studio 2013**: par défaut, les bibliothèques MFC installés dans Visual Studio 2013 prennent uniquement en charge Unicode développement. Vous devez les DLL MBCS pour créer un projet MFC dans Visual Studio 2013 a la **du jeu de caractères** propriété **utiliser le jeu de caractères codés sur plusieurs octets** ou **pas définir**. Télécharger la DLL à [bibliothèque MFC multioctet pour Visual Studio 2013](https://www.microsoft.com/en-us/download/details.aspx?id=40770).

**Visual Studio 2015**: à la fois Unicode et MBCS MFC DLL sont inclus dans les composants de programme d’installation de Visual C++, mais prise en charge des MFC n’est pas installé par défaut. Visual C++ et MFC sont des configurations dont l’installation est facultative dans le programme d’installation de Visual Studio. Pour que MFC soit installé, choisissez **Personnalisé** dans le programme d’installation et, sous **Langages de programmation**, assurez-vous que **Visual C++** et **Microsoft Foundation Classes pour C++** sont sélectionnés. Si vous avez déjà installé Visual Studio, il vous est demandé d’installer Visual C++ et/ou MFC quand vous tentez de créer un projet MFC.

**Visual Studio 2017**: le Unicode et les DLL MFC MBCS sont installés avec le **bureau développement avec C++** la charge de travail lorsque vous sélectionnez **prise en charge MFC et ATL** à partir de la  **Composants facultatifs** volet. Si votre installation n’inclut pas ces composants, vous pouvez lancer le programme d’installation à partir de la **nouveaux projets** boîte de dialogue à l’aide de la **ouvrir Visual Studio Installer** lien.

## <a name="see-also"></a>Voir aussi

[Versions de bibliothèque MFC](../mfc/mfc-library-versions.md)


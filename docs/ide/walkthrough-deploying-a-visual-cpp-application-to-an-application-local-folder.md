---
title: Déployer une Application Visual C++ dans un dossier local d’application | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- deploying Visual C++ applications
ms.assetid: 47a81c47-9dbe-47c6-96cc-fbb2fda5e6ad
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9a02e585dc2b82c8b8ad675907e4205db6ad7279
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-deploying-a-visual-c-application-to-an-application-local-folder"></a>Procédure pas à pas : déploiement d'une application Visual C++ dans un dossier local de l'application
Décrit comment déployer une application Visual C++ en copiant les fichiers dans son dossier.  
  
## <a name="prerequisites"></a>Prérequis  
  
-   Un ordinateur équipé de Visual Studio est installé.  
  
-   Un autre ordinateur qui ne dispose pas des bibliothèques Visual C++.  
  
### <a name="to-deploy-an-application-to-an-application-local-folder"></a>Pour déployer une application vers un dossier local de l’application  
  
1.  Créer et générer une application MFC en suivant les étapes dans [procédure pas à pas : déploiement d’un Visual C++ Application à l’aide d’un projet d’installation](../ide/walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md).  
  
2.  Copiez les fichiers de bibliothèque MFC et runtime C (CRT) appropriés, par exemple, pour x86 plateforme et prise en charge Unicode, copiez mfc100u.dll et msvcr100.dll à partir de \Program Files\Microsoft Visual Studio 10.0\VC\redist\x86\—and puis collez-les dans le dossier \Release\ du votre projet MFC. Pour plus d’informations sur les autres fichiers que vous aurez peut-être à copier, consultez [détermination des DLL à redistribuer](../ide/determining-which-dlls-to-redistribute.md).  
  
3.  Exécutez l’application MFC sur un deuxième ordinateur qui ne dispose pas des bibliothèques Visual C++.  
  
    1.  Copiez le contenu du dossier \Release\ et collez-les dans le dossier de l’application sur le deuxième ordinateur.  
  
    2.  Exécutez l’application sur le deuxième ordinateur.  
  
     L’application s’exécute correctement, car les bibliothèques Visual C++ sont disponibles dans le dossier local de l’application.  
  
## <a name="see-also"></a>Voir aussi  
 [Exemples de déploiement](../ide/deployment-examples.md)
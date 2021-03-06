---
title: Une Application de clr - C++ en cours d’exécution sur une Version antérieure du Runtime | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- applications [C++], runtime version specified
- versions [C++]
- app.config files, runtime version specified
- compatibility [C++], runtime version specified
- backward compatibility [C++], runtime version specified
- application deployment [C++], runtime version specified
- common language runtime [C++], version specified
- deploying applications [C++], runtime version specified
ms.assetid: 940171b7-6937-4b14-8e87-c199e23f4f2e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4f8e76930eb9191d27085d92a9d3a678812715fc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="running-a-c-clr-application-on-a-previous-runtime-version"></a>Exécution d'une application C++ /clr sur une version antérieure du runtime
Sauf indication contraire, une application C++ .NET Framework est générée doit pour s’exécuter sur la version du common language runtime (CLR) que le compilateur utilise pour générer l’application. Toutefois, il est possible pour une application .exe qui est générée pour une version du runtime à s’exécuter sur n’importe quelle autre version qui fournit les fonctionnalités requises.  
  
 Pour ce faire, fournissez un fichier app.config qui contient des informations de version d’exécution dans le `supportedRuntime` balise.  
  
 Au moment de l’exécution, le fichier app.config doit avoir un nom sous la forme *nomfichier.ext*.config, où *nomfichier.ext* est le nom du fichier exécutable ayant démarré l’application, et il doit être dans le même répertoire que le fichier exécutable. Par exemple, si votre application se nomme TestApp.exe, le fichier app.config est nommé TestApp.exe.config.  
  
 Si vous spécifiez plusieurs versions du runtime et que l’application s’exécute sur un ordinateur qui possède plusieurs versions du runtime installée, l’application utilise la première version qui est spécifiée dans le fichier de configuration et est installée.  
  
 Pour plus d’informations, consultez [Comment : configurer une application pour cibler une Version du .NET Framework](http://msdn.microsoft.com/en-us/5247b307-89ca-417b-8dd0-e8f9bd2f4717).  
  
 Pour s’exécuter sur la version 1.0 ou 1.1 du CLR, une application qui est généré par Visual C++ compilateur doit être compilé à l’aide de [/CLR : initialAppDomain](../build/reference/clr-common-language-runtime-compilation.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Déploiement d’Applications de bureau](../ide/deploying-native-desktop-applications-visual-cpp.md)
---
title: "G&#233;n&#233;ration d&#39;assemblys c&#244;te &#224; c&#244;te C/C++ | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "applications côte à côte (C++)"
ms.assetid: 7fa20b16-3737-4f76-a0b5-1dacea19a1e8
caps.latest.revision: 18
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# G&#233;n&#233;ration d&#39;assemblys c&#244;te &#224; c&#244;te C/C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un [assembly côte à côte](_win32_side_by_side_assemblies) est une collection de ressources \(un groupe de DLL, de classes de fenêtres, de serveurs COM, de bibliothèques de types ou d'interfaces\) disponibles, qu'une application peut utiliser au moment de l'exécution.  L'avantage principal du rempaquetage des DLL dans des assemblys est que plusieurs versions d'assemblys peuvent être utilisées simultanément par les applications et que la maintenance des assemblys actuellement installés peut être assurée en cas de mise à jour.  
  
 Une application Visual C\+\+ peut utiliser une ou plusieurs DLL dans diverses parties de l'application.  Pendant l'exécution, les DLL sont chargées dans le processus principal et le code requis est exécuté.  L'application se base sur le système d'exploitation pour localiser les DLL demandées, déterminer les autres DLL dépendantes devant être chargées et les charger avec la DLL demandée.  Sur les versions du système d'exploitation Windows antérieures à Windows XP, Windows Server 2003 et Windows Vista, le chargeur de système d'exploitation recherche les DLL dépendantes dans le dossier local de l'application ou un autre dossier spécifié dans le chemin d'accès système.  Sous Windows XP, Windows Server 2003 et Windows Vista, le chargeur du système d'exploitation peut également rechercher les DLL dépendantes à l'aide d'un fichier de [manifeste](http://msdn.microsoft.com/library/aa375365) et rechercher les assemblys côte à côte qui contiennent ces DLL.  
  
 Par défaut, lorsqu'une DLL est générée avec Visual Studio, elle dispose d'un [manifeste d'application](http://msdn.microsoft.com/library/aa374191) incorporé sous la forme d'une ressource RT\_MANIFEST dont l'ID est égal à 2.  Comme pour un fichier exécutable, ce manifeste décrit les dépendances de cette DLL vis\-à\-vis d'autres assemblys.  Cela suppose que la DLL ne fasse pas partie d'un assembly côte à côte et que les applications qui dépendent de cette DLL n'utilisent pas un manifeste d'application pour la charger, mais s'appuient plutôt sur le chargeur du système d'exploitation pour rechercher cette DLL dans le chemin d'accès système.  
  
> [!NOTE]
>  Il est important, pour une DLL utilisant un manifeste d'application, que ce dernier soit incorporé sous la forme d'une ressource dont l'ID est égal à 2.  Si la DLL est chargée dynamiquement lors de l'exécution \(par exemple, à l'aide de la fonction [LoadLibrary](http://msdn.microsoft.com/library/windows/desktop/ms684175)\), le chargeur du système d'exploitation charge les assemblys dépendants spécifiés dans le manifeste de la DLL.  Les manifestes d'application externes pour les DLL ne sont pas vérifiés au cours de l'appel `LoadLibrary`.  Si le manifeste n'est pas incorporé, le chargeur peut tenter de charger des versions inexactes des assemblys ou ne pas parvenir à trouver les assemblys dépendants.  
  
 Une ou plusieurs DLL connexes peuvent être rempaquetées dans un assembly côte à côte avec un [manifeste d'assembly](http://msdn.microsoft.com/library/aa374219) correspondant qui décrit les fichiers contenus dans l'assembly, ainsi que la dépendance de l'assembly vis\-à\-vis d'autres assemblys côte à côte.  
  
> [!NOTE]
>  Si un assembly contient une DLL, il vaut mieux incorporer le manifeste d'assembly dans cette DLL comme une ressource à l'ID égal à 1, et attribuer le même nom à l'assembly privé et la DLL.  Par exemple, si le nom de la DLL est mylibrary.dll, la valeur de l'attribut de nom utilisé dans l'élément \<assemblyIdentity\> du manifeste peut également être mylibrary.  Dans certains cas, lorsqu'une bibliothèque a une extension autre que .dll \(par exemple, un projet ActiveX MFC Controls crée une bibliothèque .ocx\), un manifeste d'assembly externe peut être créé.  Dans ce cas, le nom de l'assembly et de son manifeste doit être différent du nom de la DLL \(par exemple, MyAssembly, MyAssembly.manifest et mylibrary.ocx\).  Il reste cependant recommandé de renommer de telles bibliothèques avec l'extension.dll et d'incorporer le manifeste en tant que ressource afin de diminuer le futur coût de maintenance de cet assembly.  Pour plus d'informations sur la recherche d'assemblys privés par le système d'exploitation, consultez [Séquence de recherche d'assemblys](http://msdn.microsoft.com/library/aa374224).  
  
 Cette modification peut permettre de déployer les DLL correspondantes sous forme d'un [assembly privé](_win32_private_assemblies) dans un dossier local d'application ou comme un [assembly partagé](https://msdn.microsoft.com/en-us/library/aa375996.aspx) dans le cache d'assembly WinSxS.  Plusieurs étapes doivent être suivies pour que le comportement au moment de l'exécution de ce nouvel assembly soit correct ; elles sont décrites dans [Instructions relatives à la création d'assemblys côte à côte](http://msdn.microsoft.com/library/aa375155).  Une fois un assembly correctement créé, il peut être déployé en tant qu'assembly privé ou partagé en même temps qu'une application dépendante de lui.  Lorsque vous installez un assembly côte à côte en tant qu'assembly partagé, vous pouvez suivre les indications données sous [Installation d'assemblys Win32 pour le partage de composants côte à côte sur Windows XP](http://msdn.microsoft.com/library/aa369532) ou utiliser les [modules de fusion](http://msdn.microsoft.com/library/aa369820).  Lors de l'installation d'assemblys côte à côte comme un assembly privé, il vous suffit de copier la DLL, les ressources et le manifeste d'assembly correspondants au cours du processus d'installation dans le dossier local de l'application sur l'ordinateur cible, garantissant ainsi que cet assembly pourra être trouvé par le chargeur pendant l'exécution \(voir [Séquence de recherche d'assemblys](http://msdn.microsoft.com/library/aa374224)\).  Une autre méthode consiste à utiliser [Windows Installer](http://msdn.microsoft.com/library/cc185688) et suivre les indications données sous [Installation d'assemblys Win32 pour l'usage privé d'une application sur Windows XP](http://msdn.microsoft.com/library/aa369534).  
  
## Voir aussi  
 [Exemples de déploiement](../ide/deployment-examples.md)   
 [Génération d'applications isolées C\/C\+\+](../build/building-c-cpp-isolated-applications.md)   
 [Génération d'applications isolées C\/C\+\+ et d'assemblys côte à côte](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)
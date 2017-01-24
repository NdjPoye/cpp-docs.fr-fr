---
title: "D&#233;pannage d&#39;applications isol&#233;es C/C++ et d&#39;assemblys c&#244;te &#224; c&#244;te | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "dépanner les applications isolées"
  - "dépanner les assemblys côte à côte"
  - "dépanner Visual C++"
ms.assetid: 3257257a-1f0b-4ede-8564-9277a7113a35
caps.latest.revision: 28
caps.handback.revision: 28
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# D&#233;pannage d&#39;applications isol&#233;es C/C++ et d&#39;assemblys c&#244;te &#224; c&#244;te
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le chargement d'une application C\/C\+\+ peut échouer si les bibliothèques dépendantes sont introuvables.  Cet article décrit les raisons les plus courantes de l'échec du chargement d'une application C\/C\+\+, et suggère une procédure de résolution des problèmes.  
  
 Si le chargement d'une application échoue car le manifeste de l'application stipule une dépendance sur un assembly côte à côte, et que l'assembly n'est pas installé en tant qu'assembly privé dans le même dossier que l'exécutable, ni dans le cache d'assembly natif dans le dossier %WINDIR%\\WinSxS\\, l'un des messages d'erreur suivants peut s'afficher, selon la version de Windows sur laquelle vous tentez d'exécuter l'application.  
  
-   L'application n'a pas réussi à s'initialiser correctement \(0xc0000135\).  
  
-   Cette application n'a pas démarré, car la configuration de l'application est incorrecte.  Réinstaller l'application pourrait résoudre ce problème.  
  
-   Le système ne peut exécuter le programme spécifié.  
  
 Si votre application ne possède aucun manifeste et dépend d'une DLL que Windows ne peut pas trouver dans les emplacements standard de recherche, un message d'erreur semblable au suivant peut afficher :  
  
-   Cette application n'a pas pu démarrer car *une DLL requise* est introuvable.  La réinstallation de cette application peut corriger ce problème.  
  
 Si votre application est déployée sur un ordinateur qui ne dispose pas de Visual Studio, et qu'elle s'arrête avec des messages d'erreur semblables aux précédents, vérifiez les points suivants :  
  
1.  Suivez la procédure décrite dans [Fonctionnement des dépendances d'une application Visual C\+\+](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md).  Dependency Walker peut afficher la plupart des dépendances d'une application ou d'une DLL.  Si vous constatez que certaines DLL sont manquantes, installez\-les sur l'ordinateur sur lequel vous essayez d'exécuter votre application.  
  
2.  Le chargeur du système d'exploitation utilise le manifeste de l'application pour charger les assemblys dont dépend l'application.  Le manifeste peut être incorporé dans le fichier binaire en tant que ressource ou installé en tant que fichier distinct dans le dossier de l'application.  Pour vérifier si le manifeste est incorporé dans le fichier binaire, ouvrez le fichier binaire dans [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] et recherchez RT\_MANIFEST dans sa liste de ressources.  Si vous ne trouvez pas de manifeste incorporé, recherchez dans le dossier de l'application un fichier portant un nom semblable à \<nom\_fichier\_binaire\>.\<extension\>.manifest.  
  
3.  Si votre application dépend d'assemblys côte à côte et qu'un manifeste n'est pas présent, vous devez vous assurer que l'éditeur de liens génère un manifeste pour votre projet.  Cochez l'option **Génération d'un manifeste** de l'éditeur de liens dans la boîte de dialogue **Propriétés du projet** du projet.  
  
4.  Si le manifeste est incorporé dans le fichier binaire, assurez\-vous que l'ID de RT\_MANIFEST est correct pour ce type de fichier binaire.  Pour plus d'informations sur l'ID de ressource à utiliser, consultez [Utilisation d'assemblys côte à côte en tant que ressource \(Windows\)](http://msdn.microsoft.com/library/windows/desktop/aa376617.aspx).  Si le manifeste est dans un fichier distinct, ouvrez\-le dans un éditeur XML ou un éditeur de texte.  Pour plus d'informations sur les manifestes et les règles de déploiement, consultez [Manifestes](http://msdn.microsoft.com/library/aa375365).  
  
    > [!NOTE]
    >  Si un manifeste incorporé et un fichier manifeste distinct sont tous les deux présents, le chargeur du système d'exploitation utilise le manifeste incorporé et ignore le fichier distinct.  Toutefois, Windows XP fonctionne de manière inverse : le fichier manifeste distinct est utilisé et le manifeste incorporé est ignoré.  
  
5.  Nous vous recommandons d'incorporer un manifeste dans chaque DLL car les manifestes externes sont ignorés quand une DLL est chargée via un appel à `LoadLibrary`.  Pour plus d'informations, consultez [Manifestes d'assembly](http://msdn.microsoft.com/library/aa374219).  
  
6.  Vérifiez que tous les assemblys énumérés dans le manifeste sont correctement installés sur l'ordinateur.  Chaque assembly est spécifié dans le manifeste par son nom, son numéro de version et son architecture de processeur.  Si votre application dépend d'assemblys côte à côte, vérifiez que ces assemblys sont installés correctement sur l'ordinateur afin que le chargeur du système d'exploitation puisse les trouver, comme cela est décrit dans [Séquence de recherche d'assemblys](http://msdn.microsoft.com/library/aa374224).  N'oubliez pas que les assemblys 64 bits ne peuvent pas être chargés dans des processus 32 bits ni exécutés sur des systèmes d'exploitation 32 bits.  
  
## Exemple  
 Supposons que nous ayons une application, appl.exe, générée à l'aide de [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)].  Le manifeste de l'application est soit incorporé dans appl.exe en tant que ressource binaire RT\_MANIFEST, qui a un ID égal à 1, soit stocké en tant que fichier distinct appl.exe.manifest.  Le contenu de ce manifeste ressemble à ceci :  
  
```  
<assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
  <dependency>  
    <dependentAssembly>  
      <assemblyIdentity type="win32" name="Fabrikam.SxS.Library" version="2.0.20121.0" processorArchitecture="x86" publicKeyToken="1fc8b3b9a1e18e3e"></assemblyIdentity>  
    </dependentAssembly>  
  </dependency>  
</assembly>  
```  
  
 Ce manifeste indique au chargeur du système d'exploitation que le fichier appl.exe dépend d'un assembly nommé Fabrikam.SxS.Library, version 2.0.20121.0, généré pour une architecture de processeur x86 32 bits.  L'assembly côte à côte dépendant peut être installé comme un assembly partagé ou comme un assembly privé.  
  
 Dans le cas d'un assembly partagé, le manifeste de l'assembly est installé dans le dossier %WINDIR%\\WinSxS\\Manifests\\.  Il identifie l'assembly et répertorie son contenu, c'est\-à\-dire les DLL qui font partie de l'assembly :  
  
```  
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
<assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
   <noInheritable/>  
   <assemblyIdentity type="win32" name="Fabrikam.SxS.Library" version="2.0.20121.0" processorArchitecture="x86" publicKeyToken="1fc8b3b9a1e18e3e"/>  
   <file name="Fabrikam.Main.dll" hash="3ca5156e8212449db6c622c3d10f37d9adb1ab12" hashalg="SHA1"/>  
   <file name="Fabrikam.Helper.dll" hash="92cf8a9bb066aea821d324ca4695c69e55b2d1c2" hashalg="SHA1"/>  
</assembly>  
```  
  
 Les assemblys côte à côte peuvent également utiliser des [fichiers de configuration d'éditeur](http://msdn.microsoft.com/library/aa375682) \(également appelés fichiers de stratégie\) pour rediriger globalement les applications et les assemblys afin qu'ils utilisent une version donnée d'un assembly côte à côte à la place d'une autre version du même assembly.  Vous pouvez vérifier les stratégies pour un assembly partagé dans le dossier %WINDIR%\\WinSxS\\Policies\\.  Voici un exemple de fichier de stratégie :  
  
```  
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
<assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
  
   <assemblyIdentity type="win32-policy" name="policy.2.0.Fabrikam.SxS.Library" version="2.0.20121.0" processorArchitecture="x86" publicKeyToken="1fc8b3b9a1e18e3e"/>  
   <dependency>  
      <dependentAssembly>  
         <assemblyIdentity type="win32" name="Fabrikam.SxS.Library" processorArchitecture="x86" publicKeyToken="1fc8b3b9a1e18e3e"/>  
         <bindingRedirect oldVersion="2.0.10000.0-2.0.20120.99" newVersion="2.0.20121.0"/>  
      </dependentAssembly>  
   </dependency>  
</assembly>  
```  
  
 Ce fichier de stratégie spécifie que toute application ou tout assembly qui demande la version 2.0.10000.0 de cet assembly doit utiliser à la place la version 2.0.20121.0, qui est la version actuellement installée sur le système.  Si une version de l'assembly mentionné dans le manifeste de l'application est spécifiée dans le fichier de stratégie, le chargeur recherche une version de cet assembly spécifiée dans le manifeste dans le dossier %WINDIR%\\WinSxS\\, et si cette version n'est pas installée, le chargement échoue.  Et si la version 2.0.20121.0 de l'assembly n'est pas installée, le chargement échoue pour les applications qui demandent la version 2.0.10000.0 de l'assembly.  
  
 Toutefois, l'assembly peut également être installé comme un assembly côte à côte privé dans le dossier de l'application installée.  Si le système d'exploitation ne parvient pas à trouver l'assembly sous la forme d'un assembly partagé, il le cherche sous la forme d'un assembly privé, dans l'ordre suivant :  
  
1.  Recherchez dans le dossier de l'application un fichier manifeste du nom de \<nom\_assembly\>.manifest.  Dans cet exemple, le chargeur essaie de trouver Fabrikam.SxS.Library.manifest dans le dossier qui contient appl.exe.  S'il trouve ce manifeste, le chargeur charge l'assembly à partir du dossier de l'application.  Si l'assembly est introuvable, le chargement échoue.  
  
2.  Essayez d'ouvrir le dossier \\\<nom\_assembly\>\\ dans le dossier qui contient appl.exe, et si \\\<nom\_assembly\>\\ existe, essayez de charger un fichier manifeste du nom de \<nom\_assembly\>.manifest à partir de ce dossier.  S'il trouve ce manifeste, le chargeur charge l'assembly à partir du dossier \\\<nom\_assembly\>\\.  Si l'assembly est introuvable, le chargement échoue.  
  
 Pour plus d'informations sur la façon dont le chargeur recherche des assemblys dépendants, consultez [Séquence de recherche d'assemblys](http://msdn.microsoft.com/library/aa374224).  Si le chargeur ne parvient pas à trouver un assembly dépendant sous la forme d'un assembly privé, le chargement échoue et le message « Le système ne peut exécuter le programme spécifié » s'affiche.  Pour résoudre cette erreur, assurez\-vous que les assemblys dépendants \(et les DLL qui en font partie\) sont installés sur l'ordinateur en tant qu'assemblys privés ou partagés.  
  
## Voir aussi  
 [Concepts d'applications isolées et d'assemblys côte à côte](../build/concepts-of-isolated-applications-and-side-by-side-assemblies.md)   
 [Génération d'applications isolées C\/C\+\+ et d'assemblys côte à côte](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)
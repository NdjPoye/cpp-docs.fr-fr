---
title: "Visual&#160;C++ dans Visual Studio&#160;2015 | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "visual c++"
  - "visual c"
  - "vc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "code non managé, C++"
  - "environnement de développement, Visual C++"
  - "code non managé"
  - "Visual C++"
  - "Visual C++, référence"
ms.assetid: e8dcc44c-a3e2-4ffe-887c-fd15b18dc458
caps.latest.revision: 61
caps.handback.revision: 61
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Visual&#160;C++ dans Visual Studio&#160;2015
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le langage de programmation et les outils de développement [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] vous aident à développer des applications Windows universelles natives, des applications de bureau et serveur natives, des bibliothèques multiplateformes qui s’exécutent sur Android, iOS et Windows, ainsi que des applications managées qui s’exécutent sur le .NET Framework.  
  
 **À qui cette documentation est\-elle destinée ?**  
  
 Ce contenu est destiné aux développeurs C\+\+ qui écrivent des programmes.  
  
-   Si vous recherchez un package redistribuable C\+\+ et des composants d’exécution pour pouvoir exécuter un programme, accédez au [Centre de téléchargement Microsoft](http://www.microsoft.com/en-us/download/) et entrez **Visual C\+\+** dans la zone de recherche.  
  
-   Si vous recherchez une introduction aux concepts de base de la programmation en C\+\+, accédez à l’un des nombreux sites web qui offrent ce contenu ou obtenez une copie de l’ouvrage [Programming \-\- Principles and Practice Using C\+\+Programmation \(deuxième édition\)](http://stroustrup.com/Programming/) de l’inventeur du C\+\+, Bjarne Stroustrup. Le contenu Visual C\+\+ part du principe que vous avez déjà une connaissance de base de C\+\+.  
  
-   Si vous cherchez le compilateur Visual C\+\+, vous devez télécharger une édition payante ou gratuite de Visual Studio 2015 à partir du site web [https:\/\/www.visualstudio.com\/](https://www.visualstudio.com/).  
  
> [!WARNING]
>  Dans Visual Studio 2015, Visual C\+\+ n’est pas installé par défaut. Lors de l'installation, veillez à choisir l'installation **Personnalisée**, puis les composants C\+\+ dont vous avez besoin. Ou, si Visual Studio est déjà installé, choisissez **Fichier &#124; Nouveau &#124; Projet &#124; C\+\+** et vous serez invité à installer les composants nécessaires.  
  
## Informations générales à propos de Visual C\+\+  
 [Nouveautés dans Visual C\+\+](../top/what-s-new-for-visual-cpp-in-visual-studio-2015.md)  
 Découvrez les nouveautés intégrées dans Visual C\+\+.  
  
 [Modifications avec rupture dans Visual C\+\+ 2015](../porting/visual-cpp-change-history-2003-20151.md)  
 Découvrez les modifications avec rupture introduites dans cette version.  
  
 [Bienvenue dans C\+\+](../cpp/welcome-back-to-cpp-modern-cpp.md)  
 En savoir plus sur les techniques de programmation C\+\+ basées sur C\+\+11 et C\+\+14 qui vous permettent d’écrire rapidement du code sécurisé et d’éviter la plupart des pièges de la programmation de style C.  
  
 [How to Report a Problem with the Visual C\+\+ Toolset](../Topic/How%20to%20Report%20a%20Problem%20with%20the%20Visual%20C++%20Toolset.md)  
 Découvrez comment créer des rapports d’erreurs efficaces portant sur l’ensemble d’outils Visual C\+\+ \(compilateur, éditeur de liens et autres outils\) et différentes manières de soumettre votre rapport.  
  
 [Guide du portage et de la mise à niveau de Visual C\+\+](../porting/visual-cpp-porting-and-upgrading-guide.md)  
 Conseils pour le portage de code et la mise à niveau de projets vers Visual C\+\+ dans [!INCLUDE[vs_dev14](../ide/includes/vs_dev14_md.md)], notamment le portage de code C\+\+ vers Windows 10 et la plateforme Windows universelle.  
  
 [Prise en charge des fonctionnalités C\+\+11\/14\/17](../cpp/support-for-cpp11-14-17-features-modern-cpp.md)  
 Découvrez la prise en charge des fonctionnalités C\+\+11 et C\+\+14 dans Visual C\+\+.  
  
 [Blog de l’équipe Visual C\+\+](http://blogs.msdn.com/b/vcblog/)  
 Obtenez plus d’informations sur les nouvelles fonctionnalités et les informations les plus récentes des développeurs de [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)].  
  
 [Téléchargements de Visual Studio](http://go.microsoft.com/fwlink/?LinkId=235233)  
 Téléchargez Visual C\+\+.  
  
 [Outils et modèles Visual C\+\+ dans les éditions Visual Studio](../ide/visual-cpp-tools-and-templates-in-visual-studio-editions.md)  
 Découvrez les différentes éditions de Visual Studio.  
  
 [Plateformes prises en charge](../top/supported-platforms-visual-cpp.md)  
 Découvrez quelles plateformes sont prises en charge.  
  
 [Exemples Visual C\+\+](../top/visual-cpp-samples.md)  
 Informations sur les exemples.  
  
 [Communauté Visual Studio](http://go.microsoft.com/fwlink/?LinkId=235296)  
 Découvrez comment obtenir de l’aide, consigner des bogues et envoyer des suggestions pour Visual Studio.  
  
## Écriture d’applications en C\+\+  
 [Applications de plateforme Windows universelle](../windows/universal-windows-apps-cpp.md)  
 Recherchez des guides et du contenu de référence dans le Centre de développement Windows. Pour plus d’informations sur le développement d’applications du Windows Store, consultez [Développer des applications du Windows Store à l’aide de Visual Studio](http://go.microsoft.com/fwlink/p/?LinkId=248364) et [Feuille de route pour les applications du Windows Store en C\+\+](http://go.microsoft.com/fwlink/p/?LinkId=244654).  
  
 [Applications de bureau Windows \(Visual C\+\+\)](../windows/desktop-applications-visual-cpp.md)  
 Apprenez à créer des applications de bureau dotées d’une boucle de messages et de rappels.  
  
 [DLL en Visual C\+\+](../build/dlls-in-visual-cpp.md)  
 Découvrez comment utiliser Win32, ATL et MFC pour créer des DLL de bureau Windows, et obtenez des informations sur la façon de compiler et d’enregistrer votre DLL.  
  
 [Programmation parallèle](../parallel/parallel-programming-in-visual-cpp.md)  
 Apprenez à utiliser la bibliothèque de modèles parallèles, C\+\+ AMP, OpenMP et d’autres fonctionnalités associées au multithreading dans Windows.  
  
 [Meilleures pratiques pour la sécurité](../top/security-best-practices-for-cpp.md)  
 Apprenez à protéger des applications contre un code malveillant et une utilisation non autorisée.  
  
 [Cloud et programmation Web](../top/cloud-and-web-programming-in-visual-cpp.md)  
 En C\+\+, vous disposez de plusieurs options de connexion web et cloud.  
  
 [Accès aux données](../Topic/Data%20Access%20in%20Visual%20C++.md)  
 Connectez\-vous aux bases de données à l’aide d’ODBC et d’autres technologies d’accès de base de données.  
  
 [Texte et chaînes](../text/text-and-strings-in-visual-cpp.md)  
 En savoir plus sur l’utilisation de différents formats et encodages de texte et de chaîne pour un développement local et international.  
  
## Outils de développement C\+\+  
 Pour découvrir comment créer des projets, travailler avec des fichiers de code source, lier des bibliothèques, compiler, déboguer, profiler, déployer, etc., consultez [IDE et outils de développement](../ide/ide-and-tools-for-visual-cpp-development.md).  
  
## Référence du langage C\+\+  
 Pour plus d’informations sur le langage C\+\+, consultez [Référence du langage C\+\+](../cpp/cpp-language-reference.md).  
  
 Pour plus d’informations sur le préprocesseur C\+\+, consultez [Référence du préprocesseur C\/C\+\+](../preprocessor/c-cpp-preprocessor-reference.md).  
  
## Bibliothèques C\+\+ dans Visual Studio  
 Les sections suivantes fournissent des informations sur les différentes bibliothèques C\+\+ incluses avec Visual C\+\+.  
  
 [Référence sur les bibliothèques Runtime C](../c-runtime-library/c-run-time-library-reference.md)  
 Inclut des solutions alternatives optimisées en matière de sécurité pour les fonctions connues pour poser des problèmes de sécurité.  
  
 [Bibliothèque standard C\+\+](../standard-library/cpp-standard-library-reference.md)  
 Bibliothèque STL \(Standard Template Library\).  
  
 [Bibliothèque ATL \(Active Template Library\)](../atl/atl-com-desktop-components.md)  
 Prise en charge des applications et des composants COM.  
  
 [Bibliothèques MFC \(Microsoft Foundation Class\)](../mfc/mfc-desktop-applications.md)  
 Prise en charge pour la création d’applications de bureau dotées d’interfaces utilisateur traditionnelles ou Office.  
  
 [Bibliothèque de modèles parallèles](../parallel/concrt/parallel-patterns-library-ppl.md)  
 Algorithmes asynchrones et parallèles qui s’exécutent sur le processeur.  
  
 [C\+\+ AMP \(C\+\+ Accelerated Massive Parallelism\)](../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)  
 Algorithmes massivement parallèles qui s’exécutent sur le GPU.  
  
 [Bibliothèque de modèles Windows Runtime \(WRL\)](http://msdn.microsoft.com/library/windows/apps/hh438466.aspx)  
 Applications et composants [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)].  
  
 [Programmation .NET avec C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)  
 Programmation du Common Langage Runtime \(CLR\).  
  
 Consultez également la documentation relative à [STL\/CLR](../dotnet/stl-clr-library-reference.md) et à la [Bibliothèque de prise en charge C\+\+](../dotnet/cpp-support-library.md).  
  
## Autres bibliothèques C\+\+  
 Cette section contient des liens vers des bibliothèques qui ne sont pas incluses avec Visual Studio, mais qu’il est possible de télécharger et d’utiliser avec Visual C\+\+.  
  
 [Boost](http://www.boost.org/)  
 Une bibliothèque populaire et largement utilisée.  
  
 [Kit de développement logiciel \(SDK\) REST C\+\+](http://casablanca.codeplex.com).  
 Bibliothèque Microsoft pour communiquer avec les services web via HTTP.  
  
## Autres ressources  
 [Ressources Visual C\+\+](http://msdn.microsoft.com/vstudio/hh386302.aspx)  
 Autres ressources Visual C\+\+  
  
 [C\+\+ standard](http://isocpp.org/)  
 Découvrez C\+\+, obtenez une vue d’ensemble du langage C\+\+ moderne et bénéficiez de liens vers des ouvrages, des articles, des entretiens et des événements.  
  
 [Apprendre Visual C\+\+](http://msdn.microsoft.com/vstudio/hh386302.aspx)  
 Commencez à vous familiariser avec le langage C\+\+.  
  
## Voir aussi  
 [Référence du langage C](../c-language/c-language-reference.md)   
 [Référence sur les bibliothèques Runtime C](../c-runtime-library/c-run-time-library-reference.md)   
 [Fonctions intrinsèques du compilateur et langage assembleur](../intrinsics/compiler-intrinsics-and-assembly-language.md)
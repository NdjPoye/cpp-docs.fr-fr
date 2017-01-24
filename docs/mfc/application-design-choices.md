---
title: "Choix en mati&#232;re de conception d&#39;applications | Microsoft Docs"
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
  - "design d'application (C++), objectifs de design"
  - "design d'application (C++), applications Internet"
  - "applications (MFC), Internet"
  - "applications clientes (C++), différences par rapport aux applications serveur sur Internet"
  - "design"
  - "Internet (C++), différences par rapport aux intranets"
  - "applications Internet (C++), concevoir des applications"
  - "applications serveur, différences par rapport aux applications clientes sur Internet"
ms.assetid: 9b96172c-b4d4-4c69-bfb2-226ce0de6d08
caps.latest.revision: 12
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Choix en mati&#232;re de conception d&#39;applications
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article décrit certains problèmes de conception à prendre en compte lors de la programmation pour Internet.  
  
 Les rubriques traitées dans cet article sont les suivantes :  
  
-   [Intranet par rapport à Internet](#_core_intranet_versus_internet)  
  
-   [Application client\-serveur](#_core_client_or_server_application)  
  
-   [La page Web : HTML, les documents actifs, contrôles ActiveX](#_core_the_web_page.3a_.html.2c_.activex_documents.2c_.activex_controls)  
  
-   [Navigateur ou application autonome](#_core_browser_or_stand.2d.alone_application)  
  
-   [COM sur Internet](#_core_com_on_the_internet)  
  
-   [Services clients de téléchargement de données](#_core_client_data_download_services)  
  
 Si vous êtes prêt à l'écriture d'un programme maintenant, consultez l' [Applications de MFC d'écriture](../mfc/writing-mfc-applications.md).  
  
##  <a name="_core_intranet_versus_internet"></a> Intranet par rapport à Internet  
 De nombreuses applications exécutées sur Internet et sont accessibles à toute personne ayant un navigateur et un accès Internet.  Les entreprises implémentent également des intranets, qui sont des réseaux d'entreprise en utilisant les protocoles TCP\/IP et des navigateurs Web.  Des intranets offrent une source facile à mettre à niveau et centrale pour les informations d'entreprise.  Ils peuvent être utilisés pour mettre à niveau le logiciel, pour livrer et tabuler des sondages, for le support de vente et pour la remise d'informations.  Le tableau suivant compare les fonctionnalités Internet et des intranets.  
  
|Internet|Intranet|  
|--------------|--------------|  
|Bande passante|Bande passante élevée|  
|Réduit la sécurité des données et des systèmes|Accès sécurisé aux données et aux systèmes|  
|Contrôle minimal de contenu|Contrôle de haute de contenu|  
  
##  <a name="_core_client_or_server_application"></a> Application client\-serveur  
 Votre application peut s'exécuter sur un ordinateur client ou sur un serveur.  Votre application peut également être stockée sur un serveur, puis téléchargée sur Internet et exécutée sur un ordinateur client.  Les classes WinInet MFC sont utilisées pour les applications clientes aux fichiers téléchargés.  MFC et les classes de moniker asynchrone sont utilisés dans des fichiers téléchargés et des propriétés du contrôle.  Les classes pour les contrôles et des documents actifs ActiveX sont utilisées pour les applications clientes et des applications qui sont téléchargées du serveur pour une exécution sur un client.  
  
##  <a name="_core_the_web_page.3a_.html.2c_.activex_documents.2c_.activex_controls"></a> La page Web : HTML, les documents actifs, contrôles ActiveX  
 Microsoft propose plusieurs méthodes pour fournir le contenu d'une page Web.  Les pages Web peuvent utiliser les extensions standard HTML ou HTML, telles que l'indicateur OBJECT, pour fournir le contenu dynamique telles que les contrôles ActiveX.  
  
 Des navigateurs Web pages HTML d'affichage généralement.  Les documents actifs peuvent également afficher les données d'application dans le simple pointent\-cliquent l'interface d'un navigateur COM\- activé.  Votre serveur de document actif peut rendre votre document, cadre complet dans la zone clientèle entière, avec ses propres menus et les barres d'outils.  
  
 Les contrôles ActiveX que vous écrivez peuvent être téléchargés de façon asynchrone du serveur et être affichés sur une page Web.  Servez vous d'un langage de script tel que VBScript pour effectuer la validation côté client avant d'envoyer les informations du serveur.  
  
##  <a name="_core_browser_or_stand.2d.alone_application"></a> Navigateur ou application autonome  
 Ecrivez des contrôles ActiveX incorporés dans une page HTML et les serveurs de documents actifs affichés dans un navigateur.  Ecrivez les pages HTML qui contiennent un bouton pour envoyer une demande d'exécuter votre application ISAPI sur un serveur Web.  Ecrivez une application autonome qui utilise des protocoles Internet aux fichiers téléchargés et affiche les informations à un utilisateur, sans jamais à avoir utiliser une application de navigation.  
  
##  <a name="_core_com_on_the_internet"></a> COM sur Internet  
 Les contrôles ActiveX, les documents actifs, et des monikers asynchrones utilisent tous des technologies COM \(composant modèle objet\).  
  
 Les contrôles ActiveX fournissent du contenu dynamique aux documents et aux pages sur les sites web.  Avec COM générez des contrôles ActiveX et des documents de cadre plein qui utilisent Active documents.  
  
 Des monikers asynchrones fournissent des fonctionnalités pour permettre à un contrôle de se comporter bien dans un environnement Internet, notamment une manière incrémentielle ou progressif de télécharger les données.  Les contrôles doivent également s'exécuter correctement avec d'autres contrôles qui peuvent également récupérer les données asynchrone en même temps.  
  
##  <a name="_core_client_data_download_services"></a> Services clients de téléchargement de données  
 Deux ensembles d'API qui vous aideront à transférer des données vers le client sont WinInet et monikers asynchrones.  Si vous avez des fichiers .gif et .avi et contrôles ActiveX dans la page HTML, augmentez la réactivité à l'utilisateur en téléchargeant asynchrone, en utilisant des monikers asynchrones ou utilisez WinInet asynchrone.  
  
 Une tâche commune sur Internet transfère les données.  Si vous utilisez déjà la technologie active \(par exemple, si vous avez un contrôle ActiveX\), utilisez des monikers asynchrones progressivement pour afficher les données comme il doit télécharger.  Utilisez WinInet pour transférer des données à l'aide des protocoles Internet communs à HTTP, FTP, et le Gopher.  Les deux méthodes permettent l'indépendance de protocole, et fournissent une couche abstraite à utiliser Winsock et TCP\/IP.  Utilisez encore [Winsock](../mfc/windows-sockets-in-mfc.md) directement.  
  
 Le tableau suivant récapitule plusieurs façons d'utiliser MFC pour transférer des données sur Internet.  
  
|Utilise ce protocole .|Dans ces conditions|Utilise ces classes|  
|----------------------------|-------------------------|-------------------------|  
|[Téléchargement sur internet en utilisant des monikers asynchrones](../mfc/asynchronous-monikers-on-the-internet.md)|Pour le transfert asynchrone à COM, des contrôles ActiveX, et tout protocole Internet.|[CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md), [CDataPathProperty](../mfc/reference/cdatapathproperty-class.md)|  
|[WinInet](../mfc/win32-internet-extensions-wininet.md)|Pour les protocoles Internet pour HTTP, FTP, et le Gopher.  Les données peuvent être transférées en mode synchrone ou asynchrone et sont stockées dans un cache au niveau du système.|[CInternetSession](../mfc/reference/cinternetsession-class.md), [CFtpFileFind](../mfc/reference/cftpfilefind-class.md), [CGopherFileFind](../mfc/reference/cgopherfilefind-class.md), et beaucoup plus.|  
|[WinSock](../mfc/windows-sockets-in-mfc.md)|Pour garantir une meilleure efficacité et un contrôle maximal.  Nécessite les sockets et les protocoles TCP\/IP.|[CSocket](../mfc/reference/csocket-class.md), [CAsyncSocket](../mfc/reference/casyncsocket-class.md)|  
  
## Voir aussi  
 [Tâches de programmation Internet MFC](../mfc/mfc-internet-programming-tasks.md)   
 [Éléments fondamentaux relatifs à la programmation Internet MFC](../mfc/mfc-internet-programming-basics.md)   
 [Extension Internet Win32 \(WinInet\)](../mfc/win32-internet-extensions-wininet.md)   
 [Monikers asynchrones sur Internet](../mfc/asynchronous-monikers-on-the-internet.md)
---
title: "&#201;l&#233;ments fondamentaux relatifs &#224; la programmation Internet MFC | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "technologie active (C++)"
  - "contrôles ActiveX (C++), Internet"
  - "applications Internet (C++)"
  - "applications Internet (C++), technologie active"
  - "applications Internet (C++), contrôles ActiveX"
  - "applications Internet (C++), écrire"
  - "contenu Internet (C++)"
  - "ISAPI"
  - "ISAPI (extensions), programmer avec ISAPI"
  - "ISAPI (filtres), programmer avec ISAPI"
  - "programmation (C++), Internet"
  - "applications Web (C++), classes MFC"
  - "classes WinInet"
ms.assetid: 6df2dfd0-6e3f-4587-9d01-2a32f00f8a6f
caps.latest.revision: 18
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &#201;l&#233;ments fondamentaux relatifs &#224; la programmation Internet MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Microsoft fournit de nombreuses API pour programmer des applications clientes et serveur.  De nombreuses demandes sont écrites Internet, et à mesure que les technologies, les fonctionnalités de navigateur, et les options de sécurité changent, les nouveaux types d'applications sont écrites.  Navigateurs exécutent sur des ordinateurs clients, ce qui permet d'accéder au Web et affichage des pages HTML qui contiennent du texte, des graphiques, des contrôles ActiveX, et les documents.  Les serveurs fournissent FTP, le protocole HTTP, et les services de Gopher, et les applications d'extension serveur de test à CGI.  Votre application personnalisée peut récupérer des informations et fournir des données sur Internet.  
  
 ![Applications client et serveur](../mfc/media/vc38bq1.png "vc38BQ1")  
  
 MFC fournit les classes qui prennent en charge la programmation Internet.  Vous pouvez utiliser [COleControl](../mfc/reference/colecontrol-class.md) et [CDocObjectServer](../mfc/reference/cdocobjectserver-class.md) et les classes et de MFC pour écrire des contrôles et des documents actifs ActiveX.  Vous pouvez utiliser les classes de MFC telles que [CInternetSession](../mfc/reference/cinternetsession-class.md), [CFtpConnection](../mfc/reference/cftpconnection-class.md), et [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md) pour récupérer des fichiers et des informations en utilisant les protocoles Internet comme FTP, le protocole HTTP, et le Gopher.  
  
## Dans cette section  
  
-   [Classes MFC liées à Internet](../mfc/internet-related-mfc-classes.md)  
  
-   [Informations Internet par rubrique](../mfc/internet-information-by-topic.md)  
  
-   [Informations Internet par tâche](../mfc/internet-information-by-task.md)  
  
-   [Technologie active sur Internet](../mfc/active-technology-on-the-internet.md)  
  
-   [Éléments fondamentaux relatifs à WinInet](../mfc/wininet-basics.md)  
  
-   [Éléments fondamentaux relatifs à HTML](../mfc/html-basics.md)  
  
-   [Éléments fondamentaux relatifs à HTTP](../mfc/http-basics.md)  
  
## Rubriques connexes  
  
-   [Contrôles ActiveX sur Internet](../mfc/activex-controls-on-the-internet.md)  
  
-   [Documents actifs sur Internet](../mfc/active-documents-on-the-internet.md)  
  
-   [Monikers asynchrones sur Internet](../mfc/asynchronous-monikers-on-the-internet.md)  
  
-   [Extension Internet Win32 \(WinInet\)](../mfc/win32-internet-extensions-wininet.md)  
  
-   [Tâches de programmation Internet MFC](../mfc/mfc-internet-programming-tasks.md)  
  
-   [Choix en matière de conception d'applications](../mfc/application-design-choices.md)  
  
-   [Écriture d'applications MFC](../mfc/writing-mfc-applications.md)  
  
-   [Test des applications Internet](../mfc/testing-internet-applications.md)  
  
-   [Sécurité Internet](../mfc/internet-security-cpp.md)  
  
-   [Prise en charge ATL pour les contrôles DHTML](../atl/atl-support-for-dhtml-controls.md)  
  
##  <a name="_core_web_sites_for_more_information"></a> Sites Internet pour plus d'informations  
 Pour plus d'informations sur la technologie Microsoft Internet, consultez [MSDN \(Microsoft Developer Network\)](http://go.microsoft.com/fwlink/?LinkID=56322) le site Web. \(Liens de modifications sans préavis.\)  
  
 Ce site Web pour les développeurs contient des informations sur l'utilisation des outils de développement et technologies Microsoft, les informations essentielles sur les conférences récentes et prochaines.  Dans cette page, vous pouvez accéder à plusieurs sites associés du développeur, notamment.NET, et centres de développement XML.  Vous pouvez également télécharger la version bêta Kit de développement logiciel \(SDK\) et les exemples.  
  
 Le [World Wide Web Consortium \(W3C\)](http://go.microsoft.com/fwlink/?LinkID=37125) Publie les caractéristiques du HTML, le protocole HTTP, le CGI, et d'autres technologies Web.  
  
##  <a name="_core_more_internet_help"></a> Plus d'aide Internet  
 La section d'OLE [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)] contient des informations supplémentaires sur la programmation OLE.  Ces informations fournissent des détails sur l'utilisation des fonctions Win32 WinInet directement, plutôt que dans les classes de MFC.  Elles contiennent également des informations générales sur les technologies web.  
  
## Voir aussi  
 [MFC Internet Programming \(NIB\)](http://msdn.microsoft.com/fr-fr/0f7a1f3a-385b-4d56-a55b-0d766840c58a)
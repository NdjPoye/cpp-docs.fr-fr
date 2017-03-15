---
title: "&#201;l&#233;ments fondamentaux relatifs &#224; WinInet | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OnStatusCallback (méthode)"
  - "classes WinInet, à propos des classes WinInet"
  - "classes WinInet, afficher la progression"
ms.assetid: 665de5ac-e80d-427d-8d91-2ae466885940
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# &#201;l&#233;ments fondamentaux relatifs &#224; WinInet
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez utiliser WinInet pour ajouter la prise en charge via FTP pour télécharger et installer les fichiers de votre application.  Vous pouvez remplacer [OnStatusCallback](../Topic/CInternetSession::OnStatusCallback.md) et utiliser le paramètre `dwContext` pour fournir les informations de progression les utilisateurs voient recherchées et les fichiers téléchargés.  
  
 Cet article contient les rubriques suivantes :  
  
-   [Créez un navigateur très simple](#_core_create_a_very_simple_browser)  
  
-   [Télécharge une page Web](#_core_download_a_web_page)  
  
-   [Met un fichier sur un serveur FTP](#_core_ftp_a_file)  
  
-   [Récupérez un répertoire de Gopher](#_core_retrieve_a_gopher_directory)  
  
-   [Afficher les informations de progression pendant le transfert classe](#_core_display_progress_information_while_transferring_files)  
  
 Les extraits de code ci\-dessous montrent comment créer un simple navigateur, télécharger une page Web, un serveur un fichier, et la recherche d'un fichier de Gopher.  Ils ne sont pas concus comme des exemples complets et ne contiennent pas tous un gestionnaire d'exception.  
  
 Pour plus d'informations sur WinInet, consultez [Extensions Internet Win32 \(WinInet\)](../mfc/win32-internet-extensions-wininet.md).  
  
##  <a name="_core_create_a_very_simple_browser"></a> Créez un navigateur très simple  
 [!code-cpp[NVC_MFCWinInet#1](../mfc/codesnippet/CPP/wininet-basics_1.cpp)]  
  
##  <a name="_core_download_a_web_page"></a> Télécharge une page Web  
 [!code-cpp[NVC_MFCWinInet#2](../mfc/codesnippet/CPP/wininet-basics_2.cpp)]  
  
##  <a name="_core_ftp_a_file"></a> Met un fichier sur un serveur FTP  
 [!code-cpp[NVC_MFCWinInet#3](../mfc/codesnippet/CPP/wininet-basics_3.cpp)]  
  
##  <a name="_core_retrieve_a_gopher_directory"></a> Récupérez un répertoire de Gopher  
 [!code-cpp[NVC_MFCWinInet#4](../mfc/codesnippet/CPP/wininet-basics_4.cpp)]  
  
## Utilisez OnStatusCallback  
 Lors de l'utilisation du WinInet classe, vous pouvez utiliser le membre [OnStatusCallback](../Topic/CInternetSession::OnStatusCallback.md) de l'objet [CInternetSession](../mfc/reference/cinternetsession-class.md) de votre application pour extraire les informations d'état.  Si vous dérivez votre propre objet `CInternetSession`, remplacez `OnStatusCallback`, puis vérifiez les rappels d'état, MFC appelle la fonction `OnStatusCallback` avec les informations de progression sur toutes les activités dans cette session Internet.  
  
 Étant donné qu'une seule session peut prendre en charge plusieurs connexions \(qui, à leur durée de vie, peuvent exécuter de nombreuses opérations distinctes\), `OnStatusCallback` a besoin d'un mécanisme pour identifier chaque modification de l'état d'une connexion ou une transaction spécifique.  Ce mécanisme est fourni par le paramètre ID de contexte donné à plusieurs fonctions membres des classes de prise en charge de WinInet.  Ce paramètre est toujours de type `DWORD` et est toujours nommé `dwContext`.  
  
 Le contexte affecté à un objet particulier Internet est utilisé pour identifier l'activité les causes de l'objet dans le membre de `OnStatusCallback` de l'objet de `CInternetSession`.  L'appel à `OnStatusCallback` accepte plusieurs paramètres ; ces paramètres fonctionnent ensemble pour indiquer à l'application la progression a été effectuée pour laquelle transaction et connexion.  
  
 Lorsque vous créez un objet `CInternetSession`, vous pouvez spécifier un paramètre `dwContext` au constructeur.  `CInternetSession` lui\-même n'utilise pas l'ID du contexte ; au lieu de cela, il transmet l'ID de contexte à tout **InternetConnection**\- les objets dérivés qui n'obtiennent pas explicitement un ID du contexte de leurs propres.  Ensuite, ces objets `CInternetConnection` passeront ID de contexte le long aux objets `CInternetFile` qu'ils créent si vous ne spécifiez pas explicitement un ID différent de contexte  Si, en revanche, vous spécifiez un ID de contexte spécifique de les vôtres, l'objet et tout travail qu'elle exécute est associé à cet ID de contexte  Vous pouvez utiliser les ID de contexte pour identifier les informations d'état vous sont fournies dans votre fonction `OnStatusCallback`.  
  
##  <a name="_core_display_progress_information_while_transferring_files"></a> Afficher les informations de progression pendant le transfert classe  
 Par exemple, si vous écrivez une application qui crée une connexion à un serveur FTP à lire un fichier et se connecte également à un serveur HTTP pour obtenir une page Web, vous aurez un objet `CInternetSession`, objets `CInternetConnection` \(il est **CFtpSession** et l'autre est **CHttpSession**\), et deux objets `CInternetFile` \(un pour chaque connexion\).  Si vous définissez des valeurs par défaut utilisées pour les paramètres `dwContext`, vous ne pouvez pas faire la distinction entre les appels `OnStatusCallback` qui indiquent la progression de la connexion FTP et les appels qui indiquent la progression de la connexion HTTP.  Si vous spécifiez un ID `dwContext`, que vous pouvez ultérieurement pour tester dans `OnStatusCallback`, vous saurez les opérations a généré le rappel.  
  
## Voir aussi  
 [Éléments fondamentaux relatifs à la programmation Internet MFC](../mfc/mfc-internet-programming-basics.md)   
 [Extension Internet Win32 \(WinInet\)](../mfc/win32-internet-extensions-wininet.md)
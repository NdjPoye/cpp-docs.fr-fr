---
title: "Inscription | Microsoft Docs"
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
  - "initialiser des serveurs"
  - "installer des serveurs"
  - "applications serveur OLE, inscrire des serveurs"
  - "OLE, inscription"
  - "bases de données d'inscription"
  - "Registre, base de données d'éléments OLE"
  - "serveurs, initialiser"
  - "serveurs, installer"
ms.assetid: 991d5684-72c1-4f9e-a09a-9184ed12bbb9
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Inscription
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lorsqu'un utilisateur souhaite insérer un élément OLE dans une application OLE, présente une liste des types d'objets dans le but d'en choisir un.  OLE obtient la liste de la base de données d'inscription du système, qui contient les informations fournies par les applications serveur.  Lorsqu'un serveur s'enregistre lui\-même, les entrées qu'il place dans la base de données d'inscription du système \(le Registre\) décrivent chaque type d'objet qu'il fournit, les extensions de fichier, le chemin d'accès à lui\-même, parmi d'autres informations.  
  
 Le .NET Framework et les bibliothèques de liens dynamiques \(DLL\) du système utilisent le Registre pour déterminer quels types d'éléments OLE sont disponibles dans le système.  Les DLL système OLE utilisent également le Registre pour déterminer comment lancer une application serveur lorsqu'un objet lié ou incorporé est activé.  
  
 \+Cet article explique que chaque application serveur doit effectuer lorsqu'elle est installée et chaque fois qu'elle est exécutée.  
  
 Pour plus d'informations sur la base de données d'inscription du système et le format des fichiers de .reg utilisés pour le mettre à jour, consultez *la OLE guide de référence du programmeur*.  
  
##  <a name="_core_server_installation"></a> installation de serveur  
 Lors de l'installation initiale de votre application serveur, elle doit signaler tous les types de OLE éléments qu'il prend en charge.  Il est également possible d'effectuer la mise à jour sur le serveur de la base de données d'inscription du système à chaque fois qu'elle est exécutée comme une application autonome.  Cela maintient la base de données d'inscription à jour si le fichier exécutable du serveur est déplacé.  
  
> [!NOTE]
>  Les applications de MFC générées par l'application Assistant s'enregistrent automatiquement eux \- mêmes quand ils sont exécutées en tant qu'applications autonomes.  
  
 Si vous voulez enregistrer votre application pendant l'installation, utilisez l'outil de regedit.exe. \(Dans Windows 95, Windows 98 et Windows, Millenium Edition, RegEdit se trouve dans le répertoire Windows.  Dans Windows NT et Windows 2000, RegEdit se trouve dans le dossier windows System32.\) Si vous incluez un programme d'installation avec votre application, leur « RegEdit exécuté par programme d'installation *appname.reg*\/S ». \(L'indicateur de \/S indique l'opération silencieuse, c'est\-à\-dire qu'elle n'affiche pas la boîte de dialogue qui signale le succès de l'achèvement de la commande. Sinon, instruisez l'utilisateur RegEdit pour qu'il l'exécute manuellement.  
  
> [!NOTE]
>  Le fichier de .reg créé par l'Application n'inclut pas de chemin d'accès complet du fichier exécutable.  Le programme d'installation doit modifier le fichier de .reg pour inclure le chemin d'accès complet au fichier exécutable ou modifier la variable d'environnement PATH pour inclure le répertoire d'installation.  
  
 RegEdit fusionne le contenu du fichier texte de .reg dans la base de données d'inscription.  Pour vérifier la base de données ou la réparer, utilisez l'Éditeur du Registre.  Prenez soin d'éviter la suppression des entrées OLE essentielles. \(Dans Windows 95, Windows 98 et Windows, Millenium Edition, l'Éditeur du Registre est regedit.exe.  Dans Windows NT et Windows 2000, il s'agit RegEdit32.exe.\)  
  
##  <a name="_core_server_initialization"></a> Initialisation d'un serveur  
 Lorsque vous créez une application serveur avec l'Assistant d'application, l'assistant termine toutes les tâches d'initialisation automatiquement.  Cette section explique ce que vous devez suivre si vous écrivez une application serveur manuellement.  
  
 Lorsqu'une application serveur est lancée par une application conteneur, les DLL système OLE ajoutez l'option « \/Embedding » à la ligne de commande du serveur.  Un comportement de l'application serveur diffère selon qu'il a été exécuté par un conteneur, la première chose qu'une application doit effectuer option lorsqu'elle démarre l'exécution est le contrôle de la « \/Embedding » ou « \- » incorporation sur la ligne de commande.  Si ce changement existe, chargez un ensemble différent de ressources qui indiquent que le serveur comme étant actif ou ouvert entièrement sur place.  Pour plus d'informations, consultez le [Menus et de ressources : Ajouts de serveur](../mfc/menus-and-resources-server-additions.md).  
  
 Votre application serveur doit également appeler la fonction de `CWinApp::RunEmbedded` pour analyser la ligne de commande.  Si elle retourne une valeur différente de zéro, l'application ne doit pas afficher sa fenêtre si elle a été exécutée à partir d'une application conteneur, et non comme application autonome.  Cette fonction met à jour l'entrée de serveur dans la base de données d'inscription du système et appelle la fonction membre de `RegisterAll` pour vous, qui effectue l'inscription d'instance.  
  
 Lorsque votre application serveur a démarré, vous devez vous assurer qu'elle peut effectuer l'inscription d'instance.  L'inscription d'instance notifie les DLL du système OLE que le serveur sont activés et prêt à accepter des demandes des conteneurs.  Il n'ajoute pas d'entrée à la base de données d'inscription.  Exécutez l'inscription de l'instance du serveur en appelant la fonction membre de `ConnectTemplate` définie par `COleTemplateServer`.  Cela connecte l'objet de `CDocTemplate` à l'objet de `COleTemplateServer`.  
  
 La fonction de `ConnectTemplate` accepte trois paramètres : **CLSID**du serveur, un pointeur vers l'objet de `CDocTemplate`, et un indicateur qui indique si le serveur prend en charge plusieurs instances.  Un mini serveur doit prendre en charge les instances., c'est\-à\-dire qu'il est possible que plusieurs instances de serveurs s'exécutent simultanément, un pour chaque conteneur.  Par conséquent, exécutez **TRUE** pour cet indicateur en lançant un mini serveur.  
  
 Si vous entrez un mini serveur par définition, il sera toujours exécuté par un conteneur.  Vous devez toujours analyser la ligne de commande pour vérifier l'option « \/Embedding ».  L'absence de cette option dans la ligne de commande indique que l'utilisateur a essayé de démarrer le miniserver comme application autonome.  Si cela se produit, enregistrez le serveur avec la base de données d'inscription système puis affichez un message informant l'utilisateur pour lancer le mini serveur d'une application conteneur.  
  
## Voir aussi  
 [OLE](../mfc/ole-in-mfc.md)   
 [Serveurs](../mfc/servers.md)   
 [CWinApp::RunAutomated](../Topic/CWinApp::RunAutomated.md)   
 [CWinApp::RunEmbedded](../Topic/CWinApp::RunEmbedded.md)   
 [COleTemplateServer Class](../mfc/reference/coletemplateserver-class.md)
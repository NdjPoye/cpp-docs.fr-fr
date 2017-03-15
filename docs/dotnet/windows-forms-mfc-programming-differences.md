---
title: "Diff&#233;rences de programmation entre Windows Forms et MFC | Microsoft Docs"
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
  - "MFC (C++), prise en charge Windows Forms"
  - "Windows Forms (C++), comparé à MFC"
ms.assetid: f3bfcf45-cfd4-45a4-8cde-5f4dbb18ee51
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# Diff&#233;rences de programmation entre Windows Forms et MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les rubriques dans [Utilisation d'un contrôle utilisateur Windows Form dans MFC](../dotnet/using-a-windows-form-user-control-in-mfc.md) décrivent la prise en charge MFC pour Windows Forms.  Si vous n'êtes pas familiarisé avec la programmation .NET Framework ou MFC, cette rubrique fournit des informations générales à propos des différences de programmation entre les deux.  
  
 Windows Forms permet de créer des applications Microsoft Windows sur le .NET Framework.  Elle met à votre disposition un ensemble de classes extensible, orienté objet et moderne, avec lequel vous pourrez développer des applications Windows élaborées.  Windows Forms vous permet de créer une application cliente élaborée capable d'accéder à un large éventail de sources de données et de fournir des options d'affichage et de modification de données à l'aide des contrôles Windows Forms.  
  
 Toutefois, si MFC vous est familier, il se peut que vous soyez habitué à créer certains types d'applications qui ne sont pas encore explicitement pris en charge dans les Windows Forms.  Les applications Windows Forms sont équivalentes aux applications de boîte de dialogue MFC.  Cependant, elles ne fournissent pas l'infrastructure permettant de prendre en charge directement d'autres types d'applications MFC, tels que le serveur\/conteneur de documents OLE, les documents ActiveX, la prise en charge Document\/Vue pour l'interface monodocument \(SDI, single\-document interface\), l'interface multidocument \(MDI, multiple\-document interface\) et plusieurs interfaces de niveau supérieur \(MTI\).  Vous pouvez écrire votre propre logique pour créer ces applications.  
  
 Pour plus d'informations sur les applications Windows Forms, consultez [Introduction aux Windows Forms](../Topic/Windows%20Forms%20Overview.md).  
  
 Pour obtenir un exemple d'application qui illustre l'utilisation des Windows Forms avec MFC, consultez [Intégration MFC et Windows Forms \(page éventuellement en anglais\)](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en).  
  
 La vue ou le document MFC et les fonctionnalités de routage des commandes ci\-dessous ne possèdent pas d'équivalent dans les Windows Forms :  
  
-   Interface intégrée  
  
     MFC gère les commandes d'échange dynamique de données \(DDE, Dynamic Data Exchange\) et les arguments de ligne de commande que le shell utilise lorsque vous cliquez avec le bouton droit sur un document et sélectionnez des verbes, tels que Open, Edit ou Print.  Windows Forms ne possède pas d'interface intégrée et ne répond pas aux verbes du shell.  
  
-   Modèles de document  
  
     Dans MFC, les modèles de document associent une vue, qui est comprise dans une fenêtre frame \(en mode MDI, SDI ou MTI\), au document que vous avez ouvert.  Windows Forms ne possède pas d'équivalent aux modèles de document.  
  
-   Documents  
  
     MFC inscrit les types de fichiers de documents et traite le type de document lors de l'ouverture d'un document à partir du shell.  Windows Forms n'inclut pas de prise en charge de document.  
  
-   États de document  
  
     MFC conserve des états modifiés pour le document.  Ainsi, lorsque vous fermez l'application, fermez la dernière vue qui contient l'application ou quittez Windows, MFC vous invite à enregistrer le document.  Windows Forms n'inclut pas de prise en charge équivalente.  
  
-   Commandes  
  
     MFC inclut le concept de commandes.  La barre de menus, la barre d'outils et le menu contextuel peuvent tous appeler la même commande, par exemple, Couper et Copier.  Dans Windows Forms, les commandes sont des événements étroitement liés d'un élément particulier de l'interface utilisateur \(tel qu'un élément de menu\) ; c'est pourquoi vous devez raccorder tous les événements de commande explicitement.  Vous pouvez également gérer plusieurs événements à l'aide d'un unique gestionnaire dans Windows Forms.  Pour plus d'informations, consultez [Connexion de plusieurs événements à un même gestionnaire d'événements dans les Windows Forms](../Topic/How%20to:%20Connect%20Multiple%20Events%20to%20a%20Single%20Event%20Handler%20in%20Windows%20Forms.md).  
  
-   Routage des commandes  
  
     Le routage des commandes MFC permet à la vue ou au document actif de traiter des commandes.  Comme la même commande a souvent des significations différentes pour des vues différentes \(par exemple, Copier se comporte différemment dans une vue d'édition de texte que dans un éditeur graphique\), les commandes doivent être traitées par la vue active.  Comme les menus et les barres d'outils Windows Forms n'offrent pas une compréhension inhérente de la vue active, vous ne pouvez pas avoir un gestionnaire différent pour chaque type de vue pour vos événements **MenuItem.Click** sans écrire de code interne supplémentaire.  
  
-   Mécanisme de mise à jour de commande  
  
     MFC inclut un mécanisme de mise à jour de commande.  En conséquence, la vue ou le document actif est responsable de l'état des éléments de l'interface utilisateur \(par exemple, l'activation ou la désactivation d'un élément de menu ou d'un bouton outil et les états vérifiés\).  Windows Forms n'offre pas d'équivalent à un mécanisme de mise à jour de commande.  
  
## Voir aussi  
 [Utilisation d'un contrôle utilisateur Windows Form dans MFC](../dotnet/using-a-windows-form-user-control-in-mfc.md)   
 [Windows Forms Walkthroughs](http://msdn.microsoft.com/fr-fr/fd44d13d-4733-416f-aefc-32592e59e5d9)
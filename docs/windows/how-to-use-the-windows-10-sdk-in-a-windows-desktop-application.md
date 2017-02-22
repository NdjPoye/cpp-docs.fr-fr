---
title: "Proc&#233;dure&#160;: utilisation du Kit de d&#233;veloppement logiciel (SDK) Windows&#160;10 dans une application de bureau Windows | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
ms.assetid: eed6421e-9355-44a6-9582-3f1d453a6d44
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# Proc&#233;dure&#160;: utilisation du Kit de d&#233;veloppement logiciel (SDK) Windows&#160;10 dans une application de bureau Windows
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Quand vous créez un projet de bureau Windows classique dans [!INCLUDE[vs_dev14](../ide/includes/vs_dev14_md.md)], il est configuré par défaut pour être généré avec le Kit de développement logiciel \(SDK\) Windows 8.1. Cette version du Kit de développement logiciel \(SDK\) Windows est compatible avec toutes les versions récentes de Windows, y compris Windows 10, mais elle ne contient pas les API et les fonctions CRT les plus récentes de Windows 10 qui se trouvent dans le SDK Windows 10. Si vous voulez utiliser les nouvelles API, vous pouvez recibler votre projet pour faire référence au Kit de développement logiciel \(SDK\) Windows 10.  
  
 Depuis [!INCLUDE[vs_dev14](../ide/includes/vs_dev14_md.md)] et le Kit de développement logiciel \(SDK\) Windows 10, la bibliothèque CRT a été séparée en deux parties, une \(ucrtbase\) qui contient les fonctions qui sont acceptables pour une utilisation dans les applications Windows universelles et une qui contient tout le reste \(vcruntime140\). Étant donné que le Kit de développement logiciel \(SDK\) Windows 10 contient de nouvelles fonctions, comme de nombreuses fonctions C99, vous devez procéder comme suit pour utiliser ces fonctions. Consultez [Fonctions de bibliothèque CRT](../c-runtime-library/crt-library-features.md).  
  
### Pour cibler le Kit de développement logiciel \(SDK\) Windows 10  
  
1.  Assurez\-vous que le Kit de développement logiciel \(SDK\) Windows 10 est installé. Le Kit de développement logiciel \(SDK\) Windows 10 est installé avec les [Outils pour Windows 10](http://go.microsoft.com/fwlink/?LinkID=617631).  
  
2.  Ouvrez le menu contextuel du nœud du projet, puis sélectionnez **Recibler la version du Kit de développement logiciel \(SDK\)**.  
  
     ![Recibler la version du Kit de développement logiciel &#40;SDK&#41;](../windows/media/retargetingwindowssdk1.png "RetargetingWindowsSDK1")  
  
     La boîte de dialogue **Examiner les actions de la solution** apparaît.  
  
     ![Réviser les actions de la solution](../windows/media/retargetingwindowssdk2.png "RetargetingWindowsSDK2")  
  
3.  Dans la liste déroulante **Version de la plateforme cible**, choisissez la version du Kit de développement logiciel \(SDK\) Windows 10 à cibler ou choisissez 8.1 si vous ne voulez pas apporter de modifications. Cliquez sur le bouton OK pour appliquer la modification.  
  
     Notez que dans ce contexte, 8.1 fait référence à la version du Kit de développement logiciel \(SDK\) Windows, qui offre une compatibilité descendante avec Windows 8, Windows Server 2012, Windows 7, Windows Server 2008 et Windows Vista.  
  
     Si cette étape est réussie, le texte suivant s'affiche dans la fenêtre Sortie :  
  
     `Fin du reciblage : 1 a réussi, 0 a échoué, 0 a été ignoré`  
  
4.  Ouvrez les propriétés du projet et, dans la section **Propriétés de configuration, Général**, notez les valeurs de **Version de la plateforme cible Windows**. Changer la valeur ici revient à suivre cette procédure. Consultez [Général, page de propriétés \(Projet\)](../ide/general-property-page-project.md).  
  
     ![Version de la plateforme cible](../windows/media/retargetingwindowssdk3.png "RetargetingWindowsSDK3")  
  
     Cette action change les valeurs des macros du projet qui incluent des chemins d'accès aux fichiers d'en\-tête et aux fichiers de la bibliothèque. Pour voir ce qui a été modifié, dans la section Répertoires Visual C\+\+ de la boîte de dialogue Propriétés du projet, choisissez une des propriétés, comme Répertoires Include, ouvrez la liste déroulante et choisissez \<Modifier\>. La boîte de dialogue **Répertoires Include** apparaît.  
  
     ![Boîte de dialogue Répertoires Include](../windows/media/retargetingwindowssdk4.png "RetargetingWindowsSDK4")  
  
     Choisissez le bouton **Macros \>\>** et faites défiler la liste des macros jusqu'aux macros du Kit de développement logiciel \(SDK\) Windows pour voir les nouvelles valeurs.  
  
     ![Macros SDK Windows](../windows/media/retargetingwindowssdk5.png "RetargetingWindowsSDK5")  
  
5.  Répétez l'opération pour les autres projets selon vos besoins et régénérez la solution.  
  
### Pour cibler le Kit de développement logiciel \(SDK\) Windows 8.1  
  
1.  Ouvrez le menu contextuel du nœud du projet, puis sélectionnez **Recibler la version du Kit de développement logiciel \(SDK\)**.  
  
2.  Dans la liste déroulante Version de la plateforme cible, choisissez 8.1.  
  
## Voir aussi  
 [Windows Desktop Applications \(Visual C\+\+\)](../windows/how-to-use-the-windows-10-sdk-in-a-windows-desktop-application.md)
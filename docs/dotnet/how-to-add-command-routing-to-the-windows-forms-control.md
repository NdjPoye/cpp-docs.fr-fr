---
title: "Comment&#160;: ajouter le routage des commandes au contr&#244;le Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "routage des commandes (C++), ajouter aux contrôles Windows Forms"
  - "Routage des commandes (C++), les contrôles Windows Forms"
ms.assetid: bf138ece-b463-442a-b0a0-de7063a760c0
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: ajouter le routage des commandes au contr&#244;le Windows Forms
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[CWinFormsView](../mfc/reference/cwinformsview-class.md) route les commandes et les messages de l’interface Utilisateur de commande de mise à jour à l’utilisateur pour lui permettre de gérer les commandes MFC (par exemple, les éléments de menu de frame et boutons de barre d’outils).  
  
 Le contrôle utilisateur utilise [ICommandTarget::Initialize](../Topic/ICommandTarget::Initialize.md) pour stocker une référence à l’objet de source de commande dans `m_CmdSrc`, comme illustré dans l’exemple suivant. Pour utiliser `ICommandTarget` vous devez ajouter une référence à mfcmifc80.dll.  
  
 `CWinFormsView` gère plusieurs des notifications d’affichage MFC communes en les envoyant au contrôle utilisateur managé. Ces notifications incluent le [OnInitialUpdate](../Topic/IView::OnInitialUpdate.md), [OnUpdate](../Topic/IView::OnUpdate.md) et [OnActivateView](../Topic/IView::OnActivateView.md) méthodes de la [IView Interface](../mfc/reference/iview-interface.md).  
  
 Cette rubrique suppose que vous avez déjà terminées [Comment : créer le contrôle utilisateur et l’héberger dans une boîte de dialogue](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md) et [Comment : créer le contrôle utilisateur et l’hôte de l’affichage MDI](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md).  
  
### <a name="to-create-the-mfc-host-application"></a>Pour créer l’application MFC hôte  
  
1.  Ouvrez la bibliothèque de contrôles Windows Forms vous avez créé dans [Comment : créer le contrôle utilisateur et l’héberger dans une boîte de dialogue](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md).  
  
2.  Ajoutez une référence à mfcmifc80.dll en double-cliquant sur le nœud du projet dans **l’Explorateur de solutions**, en sélectionnant **Ajouter**, **référence**, et en accédant à Microsoft Visual Studio 10.0\VC\atlmfc\lib.  
  
3.  Ouvrez UserControl1.Designer.cs et ajoutez l’instruction using :  
  
    ```  
    using Microsoft.VisualC.MFC;  
    ```  
  
4.  En outre, dans UserControl1.Designer.cs, remplacez cette ligne :  
  
    ```  
    partial class UserControl1  
    ```  
  
     Pour cela :  
  
    ```  
    partial class UserControl1 : System.Windows.Forms.UserControl, ICommandTarget  
    ```  
  
5.  La première ligne de la définition de classe pour ajouter cette `UserControl1`:  
  
    ```  
    private ICommandSource m_CmdSrc;  
    ```  
  
6.  Ajoutez les définitions de méthode suivantes à `UserControl1` (nous créerons l’ID du contrôle MFC dans l’étape suivante) :  
  
    ```  
    public void Initialize (ICommandSource cmdSrc)  
    {  
       m_CmdSrc = cmdSrc;  
       // need ID of control in MFC dialog and callback function   
       m_CmdSrc.AddCommandHandler(32771, new CommandHandler (singleMenuHandler));  
    }  
  
    private void singleMenuHandler (uint cmdUI)  
    {  
       // User command handler code  
       System.Windows.Forms.MessageBox.Show("Custom menu option was clicked.");  
    }  
    ```  
  
7.  Ouvrez l’application MFC que vous avez créé dans [Comment : créer le contrôle utilisateur et l’hôte de l’affichage MDI](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md).  
  
8.  Ajoutez une option de menu qui appelle `singleMenuHandler`.  
  
     Accédez à **affichage des ressources** (Ctrl + Maj + E), développez le **Menu** dossier et double-cliquez sur **IDR_MFC02TYPE**. Cela affiche l’éditeur de menu.  
  
     Ajouter une option de menu en bas de la **vue** menu. Notez l’ID de l’option de menu dans le **propriétés** fenêtre. Enregistrez le fichier.  
  
     Dans **l’Explorateur de solutions**, ouvrez le fichier Resource.h, copiez la valeur d’ID de l’option de menu que vous venez d’ajouter et collez cette valeur comme premier paramètre à la `m_CmdSrc.AddCommandHandler` appeler dans du projet c# `Initialize` (méthode) (en remplaçant `32771` si nécessaire).  
  
9. Générez et exécutez le projet.  
  
     Dans le menu **Générer** , cliquez sur **Générer la solution**.  
  
     Sur le **Debug** menu, cliquez sur **Démarrer sans débogage**.  
  
     Sélectionnez l’option de menu que vous avez ajouté. Notez que la méthode dans le fichier .dll est appelée.  
  
## <a name="see-also"></a>Voir aussi  
 [Hébergement d’un contrôle utilisateur Windows Forms en tant que vue MFC](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)   
 [Interface de ICommandSource](../mfc/reference/icommandsource-interface.md)   
 [Interface de ICommandTarget](../mfc/reference/icommandtarget-interface.md)   
 [CommandHandler](../Topic/CommandHandler%20Delegate.md)
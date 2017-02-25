---
title: "CDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDialog class"
  - "boîtes de dialogue MFC, classe de base"
  - "boîtes de dialogue modales, créer"
  - "boîtes de dialogue non modales, créer"
  - "boîtes de dialogue non modales, afficher"
ms.assetid: ca64b77e-2cd2-47e3-8eff-c2645ad578f9
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe de base utilisée pour afficher des boîtes de dialogue sur l'écran.  
  
## Syntaxe  
  
```  
class CDialog : public CWnd  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CDialog::CDialog](../Topic/CDialog::CDialog.md)|Construit un objet `CDialog`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CDialog::Create](../Topic/CDialog::Create.md)|Initialise l'objet `CDialog`.  Crée une boîte de dialogue non modale et la attaché à l'objet d' `CDialog` .|  
|[CDialog::CreateIndirect](../Topic/CDialog::CreateIndirect.md)|Crée une boîte de dialogue non modale d'un modèle de boîte de dialogue en mémoire \(pas ressource basée\).|  
|[CDialog::DoModal](../Topic/CDialog::DoModal.md)|Appelle une boîte de dialogue modale et retourne une fois terminé.|  
|[CDialog::EndDialog](../Topic/CDialog::EndDialog.md)|Ferme une boîte de dialogue modale.|  
|[CDialog::GetDefID](../Topic/CDialog::GetDefID.md)|Obtient l'ID du contrôle bouton poussoir par défaut pour une boîte de dialogue.|  
|[CDialog::GotoDlgCtrl](../Topic/CDialog::GotoDlgCtrl.md)|Déplace le focus sur un contrôle spécifié de boîte de dialogue dans la boîte de dialogue.|  
|[CDialog::InitModalIndirect](../Topic/CDialog::InitModalIndirect.md)|Crée une boîte de dialogue modale d'un modèle de boîte de dialogue en mémoire \(pas ressource basée\).  Les paramètres sont stockés jusqu'à ce que la fonction `DoModal` soit appelée.|  
|[CDialog::MapDialogRect](../Topic/CDialog::MapDialogRect.md)|Convertit les unités de boîte de dialogue d'un rectangle pour examiner les unités.|  
|[CDialog::NextDlgCtrl](../Topic/CDialog::NextDlgCtrl.md)|Déplace le focus vers le contrôle de boîte de dialogue dans la boîte de dialogue.|  
|[CDialog::OnInitDialog](../Topic/CDialog::OnInitDialog.md)|Substitution pour augmenter l'initialisation de boîte de dialogue.|  
|[CDialog::OnSetFont](../Topic/CDialog::OnSetFont.md)|Substitution pour spécifier la police à un contrôle de boîte de dialogue est à utiliser lorsqu'il dessine du texte.|  
|[CDialog::PrevDlgCtrl](../Topic/CDialog::PrevDlgCtrl.md)|Déplace le focus sur le contrôle précédent de boîte de dialogue dans la boîte de dialogue.|  
|[CDialog::SetDefID](../Topic/CDialog::SetDefID.md)|Modifie le contrôle bouton poussoir par défaut pour une boîte de dialogue en bouton poussoir spécifié.|  
|[CDialog::SetHelpID](../Topic/CDialog::SetHelpID.md)|Définit un ID d'aide contextuelle pour la boîte de dialogue.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CDialog::OnCancel](../Topic/CDialog::OnCancel.md)|Substitution pour exécuter l'action de bouton Annuler ou de touche Échap.  La valeur par défaut ferme la boîte de dialogue et retourne **IDCANCEL**de **DoModal** .|  
|[CDialog::OnOK](../Topic/CDialog::OnOK.md)|Substitution pour exécuter l'action de bouton OK dans une boîte de dialogue modale.  La valeur par défaut ferme la boîte de dialogue et retourne **IDOK**d' `DoModal` .|  
  
## Notes  
 Les boîtes de dialogue sont de deux types : modales et non modales.  Une boîte de dialogue modale doit être fermée par l'utilisateur avant que l'application continue.  Une boîte de dialogue non modale permet à l'utilisateur d'afficher la boîte de dialogue et retourner à une autre tâche sans annuler ou supprimer la boîte de dialogue.  
  
 Un objet d' `CDialog` est une combinaison d'un modèle de boîte de dialogue et d'un `CDialog`classe dérivée.  Utilisez l'éditeur de boîtes de dialogue pour créer le modèle de boîte de dialogue et le stocker dans une ressource, puis utilisez l'assistant de classe d'ajout pour créer une classe dérivée d' `CDialog`.  
  
 Une boîte de dialogue, comme toute autre fenêtre, reçoit des messages des fenêtres.  Dans une boîte de dialogue, vous êtes particulièrement intéressé par les messages de notification de gestion des contrôles de la boîte de dialogue depuis qui permet à l'utilisateur interagit avec votre boîte de dialogue.  Utilisez la fenêtre Propriétés pour sélectionner les messages que vous souhaitez gérer et il ajoute les entrées de la table des messages et les fonctions membres gestionnaires de messages appropriées à la classe pour vous.  Vous devez seulement écrire du code spécifique à l'application dans les fonctions membres de gestionnaire.  
  
 Si vous préférez, vous pouvez toujours écrire des entrées de la table des messages et des fonctions membres manuellement.  
  
 Dans tous mais la boîte de dialogue la plus triviale, vous ajoutez des variables membres à votre classe de boîte de dialogue dérivée pour stocker des données entrées dans les contrôles de la boîte de dialogue par l'utilisateur ou pour afficher des données pour l'utilisateur.  Vous pouvez utiliser l'assistant variable d'ajouter pour créer des variables membres et les associer à des contrôles.  En même temps, vous sélectionnez un type de variable et une plage de valeurs autorisée pour chaque variable.  l'Assistant Code ajoute les variables membres à votre classe de boîte de dialogue dérivée.  
  
 Une configuration de données est générée pour gérer automatiquement l'échange de données entre les variables membres et les contrôles de la boîte de dialogue.  La configuration de données fournit les fonctions qui initialisent les contrôles de la boîte de dialogue avec les valeurs correctes, de récupérer les données, et valider les données.  
  
 Pour créer une boîte de dialogue modale, construisez un objet sur la pile à l'aide de le constructeur pour votre classe de boîte de dialogue dérivée puis appelez `DoModal` pour créer la fenêtre de dialogue et ses contrôles.  Si vous souhaitez créer une boîte de dialogue non modale, appelez **Créer** dans le constructeur de la classe de boîte de dialogue.  
  
 Vous pouvez également créer un modèle dans la mémoire à l'aide d'une structure de données de [DLGTEMPLATE](http://msdn.microsoft.com/library/windows/desktop/ms645394) comme décrit dans [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  Après avoir construit un objet d' `CDialog` , appelez [CreateIndirect](../Topic/CDialog::CreateIndirect.md) pour créer une boîte de dialogue non modale, ou l'appel [InitModalIndirect](../Topic/CDialog::InitModalIndirect.md) et [DoModal](../Topic/CDialog::DoModal.md) pour créer une boîte de dialogue modale.  
  
 La configuration de données d'échange et de validation est écrite dans une substitution d' `CWnd::DoDataExchange` qui est ajoutée à votre classe de boîte de dialogue.  Consultez la fonction membre de [DoDataExchange](../Topic/CWnd::DoDataExchange.md) dans `CWnd` pour plus d'informations sur la fonctionnalité de pagination et de validation.  
  
 Le programmeur et l'infrastructure appelle `DoDataExchange` indirectement via un appel à [CWnd::UpdateData](../Topic/CWnd::UpdateData.md).  
  
 L'infrastructure appelle `UpdateData` lorsque l'utilisateur clique sur le bouton OK pour fermer la boîte de dialogue modale.  \(Les données ne sont pas récupérées si le bouton Annuler est sélectionné.\) L'implémentation par défaut d' [OnInitDialog](../Topic/CDialog::OnInitDialog.md) appelle également `UpdateData` pour définir les valeurs initiales des contrôles.  Vous substituez en général `OnInitDialog` pour initialiser davantage les contrôles.  `OnInitDialog` est appelé une fois tous les contrôles de boîte de dialogue sont créés et juste avant la boîte de dialogue s'affiche.  
  
 Vous pouvez appeler `CWnd::UpdateData` à tout moment pendant l'exécution d'un modal ou d'une boîte de dialogue non modale.  
  
 Si vous développez une boîte de dialogue manuellement, vous ajoutez des variables membres nécessaires à la classe de boîte de dialogue dérivée vous\-même, et vous ajoutez des fonctions membres pour définir ou obtenir ces valeurs.  
  
 Une boîte de dialogue modale se ferme automatiquement lorsque l'utilisateur appuie sur OK ou les boutons Annuler ou lorsque votre code appelle la fonction membre d' `EndDialog` .  
  
 Lorsque vous implémentez une boîte de dialogue non modale, toujours substituer la fonction membre d' `OnCancel` et appelez `DestroyWindow` de lui.  N'appelez pas la classe de base `CDialog::OnCancel`, car elle appelle `EndDialog`, qui rendra la boîte de dialogue invisible mais ne le perd pas.  Vous devez également substituer `PostNcDestroy` des boîtes de dialogue non modale pour supprimer **this**, comme les boîtes de dialogue non modale et sont allouées à **nouveau**.  Les boîtes de dialogue modales sont généralement construites sur le frame et n'ont pas besoin du nettoyage de `PostNcDestroy` .  
  
 Pour plus d'informations sur `CDialog`, consultez :  
  
-   [Boîtes de dialogue](../../mfc/dialog-boxes.md)  
  
-   Article de la Base de connaissances Q262954 : HOWTO : Créez une boîte de dialogue de Resizeable avec les barres de défilement  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CDialog`  
  
## Configuration requise  
 **En\-tête :** afxwin.h  
  
## Voir aussi  
 [MFC exemple DLGCBR32](../../top/visual-cpp-samples.md)   
 [MFC exemple DLGTEMPL](../../top/visual-cpp-samples.md)   
 [CWnd, classe](../../mfc/reference/cwnd-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)
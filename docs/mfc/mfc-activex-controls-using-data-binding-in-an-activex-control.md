---
title: "Contr&#244;les ActiveX MFC&#160;: utilisation de la liaison de donn&#233;es dans un contr&#244;le ActiveX | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bindable"
  - "requestedit"
  - "defaultbind"
  - "displaybind"
  - "dispid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "contrôles dépendants (C++), ActiveX MFC"
  - "contrôles (MFC), liaison de données"
  - "liaison de données (C++), contrôles ActiveX MFC"
  - "contrôles liés aux données (C++), contrôles ActiveX MFC"
  - "contrôles ActiveX MFC, liaison de données"
ms.assetid: 476b590a-bf2a-498a-81b7-dd476bd346f1
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Contr&#244;les ActiveX MFC&#160;: utilisation de la liaison de donn&#233;es dans un contr&#244;le ActiveX
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une des utilisations les plus puissantes des contrôles ActiveX est la liaison de données, ce qui permet à une propriété du contrôle de se lier avec un champ spécifique dans une base de données.  Lorsqu'un utilisateur modifie les données de cette propriété liée, le contrôle notifie la base de données et lance une requête pour que le champ d'enregistrement soit mis à jour.  La base de données informe ensuite le contrôle de la réussite ou l'échec de la demande.  
  
 Cet article couvre le côté contrôle de la tâche.  Implémenter les interactions de liaison de données avec la base de données est la responsabilité du conteneur du contrôle.  Comment vous gérez les interactions avec la base de données dans le conteneur n'est pas traité dans cette documentation.  Comment préparer le contrôle pour la liaison de données est expliqué dans le reste de l'article.  
  
 ![Diagramme conceptuel d'un contrôle lié aux données](../mfc/media/vc374v1.png "vc374V1")  
Diagramme conceptuel d'un contrôle lié aux données  
  
 La classe `COleControl` fournit deux méthodes qui rendent la liaison de données simple à implémenter.  La première fonction, [BoundPropertyRequestEdit](../Topic/COleControl::BoundPropertyRequestEdit.md), est utilisée pour demander l'autorisation de modifier la valeur de la propriété.  [BoundPropertyChanged](../Topic/COleControl::BoundPropertyChanged.md), la deuxième fonction, est appelée une fois que la valeur de propriété a été correctement modifiée.  
  
 Cet article couvre les rubriques suivantes:  
  
-   [Créer une propriété standard pouvant être liée](#vchowcreatingbindablestockproperty)  
  
-   [Créer une méthode Get\/Set susceptible d'être liée](#vchowcreatingbindablegetsetmethod)  
  
##  <a name="vchowcreatingbindablestockproperty"></a> Créer une propriété standard pouvant être liée  
 Il est possible de créer une propriété standard liée à des données, mais il est plus probable que vous souhaitiez une [méthode get\/set liable](#vchowcreatingbindablegetsetmethod).  
  
> [!NOTE]
>  Les propriétés standard ont les attributs **bindable** et **requestedit** par défaut.  
  
#### Pour ajouter une propriété stock pouvant être liée à l'aide de l'Assistant Ajout de Propriété  
  
1.  Démarrez un projet à [Assistant Contrôle ActiveX MFC](../mfc/reference/mfc-activex-control-wizard.md).  
  
2.  Cliquez avec le bouton droit sur le nœud de l'interface pour le contrôle.  
  
     Cela ouvre le menu contextuel.  
  
3.  Dans le menu contextuel, cliquez sur **Ajouter** puis sur **Ajouter une propriété**.  
  
4.  Sélectionnez l'une des entrées dans la liste déroulante de **Propriété Nom**.  Par exemple, vous pouvez sélectionner **Texte**.  
  
     Étant donné que **Texte** est une propriété stock, les attributs **bindable** et **requestedit** sont déjà activés.  
  
5.  Activez les cases à cocher suivantes de l'onglet **Attributs IDL**: **displaybind** et **defaultbind** pour ajouter des attributs à la définition de la propriété dans le fichier .IDL du projet.  Ces attributs rendent le contrôle visible par l'utilisateur et font de la propriété standard la propriété pouvant être lié par défaut.  
  
 À ce stade, le contrôle peut afficher les données d'une source de données, mais l'utilisateur ne peut pas mettre à jour les champs de données.  Si vous souhaitez que votre contrôle puisse également mettre à jour les données, modifiez la fonction  `OnOcmCommand` [OnOcmCommand](../mfc/mfc-activex-controls-subclassing-a-windows-control.md) comme suit :  
  
 [!code-cpp[NVC_MFC_AxData#1](../mfc/codesnippet/CPP/mfc-activex-controls-using-data-binding-in-an-activex-control_1.cpp)]  
  
 Vous pouvez à présent générer le projet, qui enregistrera le contrôle.  Lorsque vous insérez le contrôle dans une boîte de dialogue, les propriétés **Data Field** et **Data Source** ont été ajoutées et vous pouvez maintenant sélectionner une source de données et un champ à afficher dans le contrôle.  
  
##  <a name="vchowcreatingbindablegetsetmethod"></a> Créer une méthode Get\/Set susceptible d'être liée  
 En plus d'une méthode get\/set liée aux données, vous pouvez également créer une [propriété standard pouvant être liée](#vchowcreatingbindablestockproperty).  
  
> [!NOTE]
>  Cette procédure suppose que vous avez un projet de contrôle ActiveX qui sous\-classes un contrôle Windows.  
  
#### Pour ajouter une méthode get\/set pouvant être liée à l'aide de l'Assistant Ajout de Propriété  
  
1.  Chargez votre projet de contrôle.  
  
2.  Dans la page de **Paramètres du contrôle**, sélectionnez une classe de fenêtre que le contrôle va sous\-classer.  Par exemple, vous pouvez vouloir sous\-classer un contrôle d'édition.  
  
3.  Chargez votre projet de contrôle.  
  
4.  Cliquez avec le bouton droit sur le nœud de l'interface pour le contrôle.  
  
     Cela ouvre le menu contextuel.  
  
5.  Dans le menu contextuel, cliquez sur **Ajouter** puis sur **Ajouter une propriété**.  
  
6.  Entrez le nom de la propriété dans la zone **Nom de propriété**.  Utilisez `MyProp` pour cet exemple.  
  
7.  Sélectionnez un type de données pour le paramètre **Type de propriété**. dans la liste déroulante.  Utilisez **short** pour cet exemple.  
  
8.  Dans **Type d'implémentation**, cliquez sur **Méthodes Get\/Set**.  
  
9. Activez les cases à cocher suivantes de l'onglet Attributs IDL : **bindable**: **requestedit**, **displaybind** et **defaultbind** pour ajouter des attributs à la définition de la propriété dans le fichier .IDL du projet.  Ces attributs rendent le contrôle visible par l'utilisateur et font de la propriété standard la propriété pouvant être liée par défaut.  
  
10. Cliquez sur **Terminer**.  
  
11. Modifiez le corps de la fonction `SetMyProp` afin qu'elle contienne le code suivant :  
  
     [!code-cpp[NVC_MFC_AxData#2](../mfc/codesnippet/CPP/mfc-activex-controls-using-data-binding-in-an-activex-control_2.cpp)]  
  
12. Le paramètre transmis aux fonctions `BoundPropertyChanged` et `BoundPropertyRequestEdit` est le dispid de la propriété, qui est le paramètre transmis à l'attribut d'id\(\) de la propriété dans le fichier .IDL.  
  
13. Modifiez la fonction [OnOcmCommand](../mfc/mfc-activex-controls-subclassing-a-windows-control.md) pour qu'elle contienne le code suivant :  
  
     [!code-cpp[NVC_MFC_AxData#1](../mfc/codesnippet/CPP/mfc-activex-controls-using-data-binding-in-an-activex-control_1.cpp)]  
  
14. Modifiez la fonction `OnDraw` afin qu'il ressemble au code ci\-dessous.  
  
     [!code-cpp[NVC_MFC_AxData#3](../mfc/codesnippet/CPP/mfc-activex-controls-using-data-binding-in-an-activex-control_3.cpp)]  
  
15. Dans la section publique du fichier d'en\-tête pour votre classe de contrôle, ajoutez les définitions suivantes \(constructeurs\) pour les attributs :  
  
     [!code-cpp[NVC_MFC_AxData#4](../mfc/codesnippet/CPP/mfc-activex-controls-using-data-binding-in-an-activex-control_4.h)]  
  
16. Procédez à la ligne suivante dans la dernière ligne de la fonction `DoPropExchange` :  
  
     [!code-cpp[NVC_MFC_AxData#5](../mfc/codesnippet/CPP/mfc-activex-controls-using-data-binding-in-an-activex-control_5.cpp)]  
  
17. Modifiez la fonction `OnResetState` afin qu'elle ressemble au code ci\-dessous.  
  
     [!code-cpp[NVC_MFC_AxData#6](../mfc/codesnippet/CPP/mfc-activex-controls-using-data-binding-in-an-activex-control_6.cpp)]  
  
18. Modifiez la fonction `GetMyProp` afin qu'elle ressemble au code ci\-dessous.  
  
     [!code-cpp[NVC_MFC_AxData#7](../mfc/codesnippet/CPP/mfc-activex-controls-using-data-binding-in-an-activex-control_7.cpp)]  
  
 Vous pouvez à présent générer le projet, qui enregistrera le contrôle.  Lorsque vous insérez le contrôle dans une boîte de dialogue, les propriétés **Data Field** et **Data Source** ont été ajoutées et vous pouvez maintenant sélectionner une source de données et un champ à afficher dans le contrôle.  
  
## Voir aussi  
 [Contrôles ActiveX MFC](../mfc/mfc-activex-controls.md)   
 [Contrôles liés aux données \(ADO et RDO\)](../data/ado-rdo/data-bound-controls-ado-and-rdo.md)
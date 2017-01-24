---
title: "Proc&#233;dure pas &#224; pas&#160;: chargement automatique d’&#233;l&#233;ments de bo&#238;te &#224; outils | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Boîte à outils (SDK Visual Studio), ajouter des contrôles en utilisant la réflexion"
  - "réflexion, boîte à outils"
ms.assetid: b03c0d62-3be0-475f-b1d9-725dee993ad6
caps.latest.revision: 56
caps.handback.revision: 56
manager: "douge"
---
# Proc&#233;dure pas &#224; pas&#160;: chargement automatique d’&#233;l&#233;ments de bo&#238;te &#224; outils
Cette procédure pas à pas illustre la façon dont un VSPackage managé peut charger automatiquement tous les éléments <xref:System.Drawing.Design.ToolboxItem> fournis par son propre assembly par le biais de la réflexion.  
  
> [!NOTE]
>  Pour ajouter des contrôles personnalisés à la boîte à outils, la méthode recommandée consiste à utiliser les modèles de contrôle de boîte à outils fournis avec le Kit de développement logiciel \(SDK\) Visual Studio, qui intègre une prise en charge du chargement automatique. Cette rubrique est conservée pour la compatibilité descendante, l’ajout des contrôles existants à la boîte à outils et le développement avancé de boîtes à outils.  
>   
>  Pour plus d’informations sur la création de contrôles de boîte à outils à l’aide de modèles, consultez [Comment : créer un contrôle de boîte à outils qui utilise Windows Forms](../misc/how-to-create-a-toolbox-control-that-uses-windows-forms.md) et [Création d’un contrôle de boîte à outils WPF](../Topic/Creating%20a%20WPF%20Toolbox%20Control.md).  
  
 Cette procédure pas à pas vous guide tout au long des étapes suivantes :  
  
1.  Ajoutez et inscrivez correctement tous les contrôles de **boîte à outils** dans les objets VSPackage à l’aide de <xref:System.ComponentModel.ToolboxItemAttribute>, <xref:System.Drawing.ToolboxBitmapAttribute> et <xref:System.ComponentModel.DisplayNameAttribute>.  
  
2.  Créez les deux contrôles suivants et ajoutez des icônes pour chacun d’eux à la **boîte à outils** :  
  
    -   Ajoutez un contrôle en utilisant une classe <xref:System.Drawing.Design.ToolboxItem> par défaut.  
  
    -   Ajoutez un autre contrôle en utilisant une classe personnalisée qui dérive de la classe <xref:System.Drawing.Design.ToolboxItem>.  
  
3.  Inscrivez le VSPackage en tant que fournisseur d’objets <xref:System.Drawing.Design.ToolboxItem> ayant la classe <xref:Microsoft.VisualStudio.Shell.ProvideToolboxItemsAttribute>.  
  
4.  Utilisez la réflexion pour générer une liste de tous les objets <xref:System.Drawing.Design.ToolboxItem> fournis par le VSPackage quand il est chargé.  
  
5.  Créez un gestionnaire pour les événements <xref:Microsoft.VisualStudio.Shell.Package.ToolboxInitialized> et <xref:Microsoft.VisualStudio.Shell.Package.ToolboxUpgraded>. Cela assure le chargement correct des objets <xref:System.Drawing.Design.ToolboxItem> du VSPackage.  
  
6.  Implémentez une commande sur le VSPackage pour forcer la réinitialisation de la **boîte à outils**.  
  
## Composants requis  
 Pour suivre cette procédure pas à pas, vous devez installer le Kit de développement logiciel \(SDK\) Visual Studio. Pour plus d'informations, consultez [Vue d’ensemble de l’extension de Visual Studio](../Topic/Extending%20Visual%20Studio%20Overview.md).  
  
## Emplacements du modèle de projet de package Visual Studio  
 Le modèle de projet de package Visual Studio se trouve à trois emplacements différents dans la boîte de dialogue **Nouveau projet** :  
  
1.  Sous l’extensibilité Visual Basic. Le langage par défaut du projet est Visual Basic.  
  
2.  Sous l’extensibilité C\#. Le langage par défaut du projet est C\#.  
  
3.  Sous l’extensibilité Autres types de projets. Le langage par défaut du projet est C\+\+.  
  
## Création d’un VSPackage managé  
  
#### Pour créer le VSPackage LoadToolboxMembers  
  
1.  Créez un VSPackage nommé `LoadToolboxMembers`. Pour plus d'informations, consultez [Procédure pas à pas : création d’une commande de menu à l’aide du modèle de package Visual Studio](../Topic/Walkthrough:%20Creating%20a%20Menu%20Command%20By%20Using%20the%20Visual%20Studio%20Package%20Template.md).  
  
2.  Ajoutez une commande de menu.  
  
     Nommez la commande `Initialize LoadToolboxMembers VB` pour Visual Basic ou `Initialize LoadToolboxMembers CS` pour Visual C\#.  
  
 Si vous suivez cette procédure pas à pas pour plusieurs langages, vous devez mettre à jour le projet pour supprimer l’ambiguïté entre les assemblys générés.  
  
#### Pour supprimer l’ambiguïté entre les VSPackages Visual Basic et Visual C\#  
  
1.  Pour [!INCLUDE[vbprvb](../dotnet/includes/vbprvb_md.md)] :  
  
    -   Dans l’**Explorateur de solutions**, ouvrez les propriétés du projet, puis sélectionnez l’onglet **Application**.  
  
         Remplacez le nom de l’assembly par `LoadToolboxMembersVB` et remplacez l’espace de noms par défaut par `Company.LoadToolboxMembersVB`.  
  
2.  Pour [!INCLUDE[csprcs](../ide/includes/csprcs_md.md)] :  
  
    1.  Dans l’**Explorateur de solutions**, ouvrez les propriétés du projet, puis sélectionnez l’onglet **Application**.  
  
         Remplacez le nom de l’assembly par `LoadToolboxMembersCS` et remplacez l’espace de noms par défaut par `Company.LoadToolboxMembersCS`.  
  
    2.  Ouvrez la classe LoadToolboxMembersPackage dans l’éditeur de code.  
  
         Pour renommer l’espace de noms existant à l’aide des outils de refactorisation, cliquez avec le bouton droit sur le nom de l’espace de noms existant, `LoadToolboxMembers`, pointez sur **Refactoriser**, puis cliquez sur **Renommer**. Remplacez le nom par `LoadToolboxMembersCS`.  
  
3.  Enregistrez toutes les modifications.  
  
#### Pour ajouter des références de prise en charge  
  
1.  Dans le projet LoadToolboxMembers, ajoutez une référence au composant <xref:System.Drawing.Design?displayProperty=fullName> du .NET Framework, comme suit.  
  
    1.  Dans l’**Explorateur de solutions**, cliquez avec le bouton droit sur le projet LoadToolboxMembers, puis cliquez sur **Ajouter**, **Référence**.  
  
    2.  Sous l’onglet **.NET** de la boîte de dialogue **Référence**, double\-cliquez sur **System.Drawing.Design**.  
  
2.  Pour Visual Basic, ajoutez les espaces de noms suivants à la liste d’espaces de noms importés dans le projet :  
  
    -   Company.LoadToolboxMembersVB  
  
    -   Système  
  
    -   System.ComponentModel  
  
    -   System.Drawing  
  
    -   System.Windows.Forms  
  
#### Pour tester le code généré  
  
1.  Compilez et démarrez le VSPackage dans la ruche expérimentale de Visual Studio.  
  
2.  Dans le menu **Outils**, cliquez sur **Initialize LoadToolboxMembers VB** ou **Initialize LoadToolboxMembers CS**.  
  
     Une boîte de message s’ouvre indiquant que le gestionnaire des éléments de menu du package a été appelé.  
  
3.  Fermez la version expérimentale de [!INCLUDE[vs_current_short](../misc/includes/vs_current_short_md.md)]..  
  
## Création d’un contrôle de boîte à outils  
 Dans cette section, vous allez créer et inscrire un contrôle utilisateur, `Control1`, qui déclare un élément de **boîte à outils** par défaut associé. Pour plus d’informations sur la façon de créer des contrôles Windows Forms et la classe <xref:System.Drawing.Design.ToolboxItem>, consultez [Développement de contrôles Windows Forms au moment du design](../Topic/Developing%20Windows%20Forms%20Controls%20at%20Design%20Time.md).  
  
#### Pour créer un contrôle de boîte à outils destiné à être utilisé avec un ToolboxItem par défaut  
  
1.  Dans l’**Explorateur de solutions**, ajoutez un objet <xref:System.Windows.Forms.UserControl> au projet LoadToolboxMembers, comme suit :  
  
    1.  Dans l’**Explorateur de solutions**, cliquez avec le bouton droit sur le projet **LoadToolboxMembers**, pointez sur **Ajouter**, puis cliquez sur **Contrôle utilisateur**.  
  
    2.  Dans la boîte de dialogue **Ajouter un nouvel élément**, remplacez le nom par `Control1.vb` pour [!INCLUDE[vbprvb](../dotnet/includes/vbprvb_md.md)] ou `Control1.cs` pour [!INCLUDE[csprcs](../ide/includes/csprcs_md.md)].  
  
         Pour plus d’informations sur la façon d’ajouter de nouveaux éléments à un projet, consultez [NIB : Comment : ajouter de nouveaux éléments de projet](http://msdn.microsoft.com/fr-fr/63d3e16b-de6e-4bb5-a0e3-ecec762201ce).  
  
     Le nouveau contrôle s’ouvre en mode Création.  
  
2.  À partir de la **boîte à outils**, faites glisser un contrôle **Button** \(situé dans la catégorie **Contrôles communs**\) vers le concepteur.  
  
3.  Double\-cliquez sur le bouton que vous venez de créer. Un gestionnaire d’événements est alors généré pour l’événement <xref:System.Windows.Forms.Control.Click> du bouton. Mettez à jour le gestionnaire d’événements en utilisant le code suivant :  
  
     [!code-cs[LoadToolboxMembers#01](../misc/codesnippet/CSharp/walkthrough-autoloading-toolbox-items_1.cs)]
     [!code-vb[LoadToolboxMembers#01](../misc/codesnippet/VisualBasic/walkthrough-autoloading-toolbox-items_1.vb)]  
  
4.  Modifiez le constructeur du contrôle pour définir le texte du bouton après que la méthode `InitializeComponent` est appelée :  
  
     [!code-cs[LoadToolboxMembers#02](../misc/codesnippet/CSharp/walkthrough-autoloading-toolbox-items_2.cs)]
     [!code-vb[LoadToolboxMembers#02](../misc/codesnippet/VisualBasic/walkthrough-autoloading-toolbox-items_2.vb)]  
  
5.  Ajoutez des attributs au fichier pour permettre au VSPackage d’interroger la classe <xref:System.Drawing.Design.ToolboxItem> fournie :  
  
     [!code-cs[LoadToolboxMembers#03](../misc/codesnippet/CSharp/walkthrough-autoloading-toolbox-items_3.cs)]
     [!code-vb[LoadToolboxMembers#03](../misc/codesnippet/VisualBasic/walkthrough-autoloading-toolbox-items_3.vb)]  
  
6.  Enregistrez le fichier.  
  
 Dans la procédure suivante, vous allez créer et inscrire un deuxième contrôle utilisateur, `Control2`, ainsi qu’un élément de **boîte à outils** personnalisé associé, `Control2_ToolboxItem`, qui est dérivé de la classe <xref:System.Drawing.Design.ToolboxItem>.  
  
#### Pour créer un contrôle de boîte à outils en vue d’utiliser une classe personnalisée dérivée de ToolboxItem  
  
1.  Créez un deuxième contrôle utilisateur nommé `Control2`. Double\-cliquez sur le formulaire pour afficher le fichier de code.  
  
2.  Ajoutez `System.Drawing.Design` et `System.Globalization` aux espaces de noms utilisés dans la classe.  
  
     [!code-cs[LoadToolboxMembers#04](../misc/codesnippet/CSharp/walkthrough-autoloading-toolbox-items_4.cs)]
     [!code-vb[LoadToolboxMembers#04](../misc/codesnippet/VisualBasic/walkthrough-autoloading-toolbox-items_4.vb)]  
  
3.  Ajoutez un gestionnaire d’événements de bouton et de clic de bouton et mettez à jour le constructeur du contrôle comme vous l’avez fait pour le premier contrôle.  
  
4.  Ajoutez les attributs <xref:System.ComponentModel.DisplayNameAttribute>, <xref:System.ComponentModel.DescriptionAttribute>, <xref:System.ComponentModel.ToolboxItemAttribute> et <xref:System.Drawing.ToolboxBitmapAttribute> au fichier.  
  
     Ces attributs permettent au VSPackage de rechercher une classe <xref:System.Drawing.Design.ToolboxItem> via une requête.  
  
     Pour obtenir des informations et des exemples supplémentaires sur la façon d’écrire des objets <xref:System.Drawing.Design.ToolboxItem> personnalisés, consultez l’exposé à la page de référence <xref:System.Drawing.Design.ToolboxItem>.  
  
     Compte tenu des modifications précédentes, votre deuxième classe de contrôle doit ressembler au code suivant. Le symbole `Control2_ToolboxMenu` reste non défini jusqu’à la fin de l’étape suivante.  
  
     [!code-cs[LoadToolboxMembers#05](../misc/codesnippet/CSharp/walkthrough-autoloading-toolbox-items_5.cs)]
     [!code-vb[LoadToolboxMembers#05](../misc/codesnippet/VisualBasic/walkthrough-autoloading-toolbox-items_5.vb)]  
  
5.  Créez une classe nommée `Control2_ToolboxItem`. Ce <xref:System.Drawing.Design.ToolboxItem> est construit pour le deuxième contrôle et ajouté à la **boîte à outils**. L’attribut `SerializableAttribute` doit être appliqué à la classe.  
  
     [!code-cs[LoadToolboxMembers#06](../misc/codesnippet/CSharp/walkthrough-autoloading-toolbox-items_6.cs)]
     [!code-vb[LoadToolboxMembers#06](../misc/codesnippet/VisualBasic/walkthrough-autoloading-toolbox-items_6.vb)]  
  
6.  Enregistrez le fichier.  
  
## Incorporation d’icônes bitmap  
 Les deux instances de <xref:System.Drawing.ToolboxBitmapAttribute> utilisées précédemment indiquent que le projet représente les deux contrôles en utilisant les icônes suivantes :  
  
-   `Control1.bmp`, située dans l’espace de noms qui contient le premier contrôle,  
  
-   `Control2.bmp`, située dans l’espace de noms qui contient le deuxième contrôle.  
  
#### Pour incorporer des icônes bitmap pour le ToolboxItem  
  
1.  Ajoutez deux nouvelles bitmaps au projet, comme suit.  
  
    1.  Cliquez avec le bouton droit sur le projet `LoadToolboxMembers`.  
  
    2.  Pointez sur **Ajouter**, puis cliquez sur **Nouvel élément**.  
  
    3.  Dans la boîte de dialogue **Ajouter un nouvel élément**, sélectionnez **Fichier bitmap**, puis nommez le fichier `Control1.bmp`.  
  
    4.  Répétez ces étapes pour la deuxième bitmap et nommez\-la `Control2.bmp`.  
  
         Chaque bitmap s’ouvre alors dans l’éditeur de bitmaps de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)].  
  
2.  Attribuez à chaque icône une taille de 16 x 16, comme suit.  
  
    1.  Pour chaque bitmap, cliquez sur **Fenêtre Propriétés** dans le menu **Affichage**.  
  
    2.  Dans la fenêtre **Propriétés**, fixez la **Hauteur** et la **Largeur** à 16.  
  
3.  Utilisez l’éditeur de bitmaps de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] pour créer une image pour chaque icône.  
  
4.  Dans l’**Explorateur de solutions**, cliquez sur chaque fichier bitmap puis, dans la fenêtre **Propriétés**, définissez la propriété **Action de génération** sur **Ressource incorporée**.  
  
5.  Enregistrez tous les fichiers ouverts.  
  
## Modification de l’implémentation du VSPackage  
 Vous devez modifier l’implémentation par défaut du VSPackage de façon à effectuer les opérations suivantes :  
  
-   Inscription de la prise en charge comme fournisseur d’éléments de **boîte à outils**.  
  
-   Obtention de la liste d’objets <xref:System.Drawing.Design.ToolboxItem> pris en charge par le VSPackage.  
  
-   Chargement de l’objet <xref:System.Drawing.Design.ToolboxItem> dans la [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] **boîte à outils** quand les événements <xref:Microsoft.VisualStudio.Shell.Package.ToolboxInitialized> et <xref:Microsoft.VisualStudio.Shell.Package.ToolboxUpgraded> sont gérés.  
  
 La procédure suivante montre comment modifier l’implémentation du package.  
  
#### Pour modifier l’implémentation du package de façon à être un fournisseur d’éléments de boîte à outils pour le VSPackage  
  
1.  Ouvrez le fichier LoadToolboxMembersPackage.cs ou LoadToolboxMembersPackage.vb dans l’éditeur de code.  
  
2.  Modifiez la déclaration de la classe `LoadToolboxMembersPackage`, qui est l’implémentation de la classe <xref:Microsoft.VisualStudio.Shell.Package> dans la solution, comme suit.  
  
    1.  Ajoutez les directives d’espace de noms suivantes au fichier de classe `LoadToolboxMembersPackage`.  
  
         [!code-cs[LoadToolboxMembers#07](../misc/codesnippet/CSharp/walkthrough-autoloading-toolbox-items_7.cs)]
         [!code-vb[LoadToolboxMembers#07](../misc/codesnippet/VisualBasic/walkthrough-autoloading-toolbox-items_7.vb)]  
  
    2.  Inscrivez le VSPackage en tant que classe <xref:System.Drawing.Design.ToolboxItem> en ajoutant une instance de <xref:Microsoft.VisualStudio.Shell.ProvideToolboxItemsAttribute>.  
  
        > [!NOTE]
        >  Le seul argument de <xref:Microsoft.VisualStudio.Shell.ProvideToolboxItemsAttribute> est la version de <xref:System.Drawing.Design.ToolboxItem> qui est fournie par le VSPackage. Le fait de modifier cette valeur force l’IDE à charger le VSPackage même s’il possède une version précédemment mise en cache de la classe <xref:System.Drawing.Design.ToolboxItem>.  
  
    3.  Ajoutez les deux nouveaux champs `private` ci\-après à la classe `LoadToolboxMembersPackage` :  
  
         Un membre <xref:System.Collections.ArrayList>, nommé `ToolboxItemList`, pour conserver la liste des objets <xref:System.Drawing.Design.ToolboxItem> gérés par la classe `LoadToolboxMembersPackage`.  
  
         Un <xref:System.String>, nommé `CategoryTab`, qui contient la catégorie ou l’onglet **Boîte à outils** qui sert à conserver les objets <xref:System.Drawing.Design.ToolboxItem> gérés par la classe `LoadToolboxMembersPackage`.  
  
     À l’issue de cette modification, voici à quoi ressemble le code :  
  
     [!code-cs[LoadToolboxMembers#08](../misc/codesnippet/CSharp/walkthrough-autoloading-toolbox-items_8.cs)]
     [!code-vb[LoadToolboxMembers#08](../misc/codesnippet/VisualBasic/walkthrough-autoloading-toolbox-items_8.vb)]  
  
3.  Développez la région Package Members pour modifier la méthode `Initialize` de sorte qu’elle effectue les opérations suivantes :  
  
    -   Pour [!INCLUDE[csprcs](../ide/includes/csprcs_md.md)], abonnement aux événements <xref:Microsoft.VisualStudio.Shell.Package.ToolboxInitialized> et <xref:Microsoft.VisualStudio.Shell.Package.ToolboxUpgraded>.  
  
    -   Appel de la méthode `CreateItemList` pour remplir l’objet <xref:System.Collections.ArrayList>`ToolboxItemList`.`ToolboxItemList` contient la liste de tous les éléments de boîte à outils gérés par `LoadToolboxMembersPackage`.  
  
     [!code-cs[LoadToolboxMembers#09](../misc/codesnippet/CSharp/walkthrough-autoloading-toolbox-items_9.cs)]
     [!code-vb[LoadToolboxMembers#09](../misc/codesnippet/VisualBasic/walkthrough-autoloading-toolbox-items_9.vb)]  
  
4.  Ajoutez deux méthodes, `CreateItemList` et `CreateToolboxItem`, à la construction, en utilisant des métadonnées, des instances des objets <xref:System.Drawing.Design.ToolboxItem> disponibles dans l’assembly `LoadToolboxMembers`, comme suit :  
  
     [!code-cs[LoadToolboxMembers#10](../misc/codesnippet/CSharp/walkthrough-autoloading-toolbox-items_10.cs)]
     [!code-vb[LoadToolboxMembers#10](../misc/codesnippet/VisualBasic/walkthrough-autoloading-toolbox-items_10.vb)]  
  
5.  Implémentez la méthode `OnRefreshToolbox` pour gérer les événements <xref:Microsoft.VisualStudio.Shell.Package.ToolboxInitialized> et <xref:Microsoft.VisualStudio.Shell.Package.ToolboxUpgraded>.  
  
     La méthode `OnRefreshToolbox` utilise la liste d’objets <xref:System.Drawing.Design.ToolboxItem> contenue dans le membre `ToolboxItemList` de la classe `LoadToolboxMembersPackage`. De même, elle effectue les opérations suivantes :  
  
    -   Suppression de tous les objets <xref:System.Drawing.Design.ToolboxItem> déjà présents dans la catégorie Boîte à outils définie par la variable `CategoryTab`.  
  
    -   Ajout de nouvelles instances de tous les objets <xref:System.Drawing.Design.ToolboxItem> répertoriés dans `ToolboxItemList` à l’onglet de catégorie du VSProject.  
  
    -   Définition de l’onglet actif **Boîte à outils** comme étant l’onglet de catégorie du VSProject.  
  
     [!code-cs[LoadToolboxMembers#11](../misc/codesnippet/CSharp/walkthrough-autoloading-toolbox-items_11.cs)]
     [!code-vb[LoadToolboxMembers#11](../misc/codesnippet/VisualBasic/walkthrough-autoloading-toolbox-items_11.vb)]  
  
    > [!NOTE]
    >  En guise d’exercice, vous pourriez développer un mécanisme visant à tester la version du VSPackage ou des éléments, et ne procéder à une mise à jour que si la version du VSPackage ou du <xref:System.Drawing.Design.ToolboxItem> a changé.  
  
## Initialisation de la boîte à outils  
  
#### Pour implémenter une commande destinée à initialiser la boîte à outils  
  
-   Modifiez la méthode de gestionnaire de commandes d’éléments de menu, `MenuItemCallBack`, comme suit.  
  
    1.  Remplacez l’implémentation existante de `MenuItemCallBack` par le code suivant :  
  
         [!code-cs[LoadToolboxMembers#12](../misc/codesnippet/CSharp/walkthrough-autoloading-toolbox-items_12.cs)]
         [!code-vb[LoadToolboxMembers#12](../misc/codesnippet/VisualBasic/walkthrough-autoloading-toolbox-items_12.vb)]  
  
## Génération et exécution de la solution  
 Vous pouvez tester le produit de cette procédure pas à pas en utilisant une instance de Visual Studio qui s’exécute dans la ruche expérimentale.  
  
#### Pour tester cette procédure pas à pas  
  
1.  Dans Visual Studio, dans le menu **Générer**, cliquez sur **Régénérer la solution**.  
  
2.  Appuyez sur F5 pour démarrer une deuxième instance de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] dans la ruche expérimentale du Registre.  
  
     Pour plus d’informations sur la façon d’utiliser la ruche expérimentale, consultez [L'Instance expérimentale](../Topic/The%20Experimental%20Instance.md).  
  
3.  Cliquez sur le menu **Outils**.  
  
     Une commande nommée **Initialize ItemConfiguration VB** ou **Initialize ItemConfiguration CS** doit figurer en haut du menu, avec une icône qui a la valeur 1.  
  
4.  Créez une application [!INCLUDE[csprcs](../ide/includes/csprcs_md.md)] ou [!INCLUDE[vbprvb](../dotnet/includes/vbprvb_md.md)]Windows Forms.  
  
     Un concepteur basé sur <xref:System.Windows.Forms.Form> doit s’afficher.  
  
5.  Faites glisser l’un des nouveaux contrôles \(ou les deux\) de la catégorie **LoadToolboxMembers Walkthrough VB** ou **LoadToolboxMembers Walkthrough CS** de la **boîte à outils** vers le formulaire du concepteur.  
  
    > [!NOTE]
    >  Si la **boîte à outils** ne s’affiche pas, cliquez sur **Boîte à outils** dans le menu **Affichage**. Si l’onglet de catégorie du VSPackage ne figure pas dans la **boîte à outils**, réinitialisez la **boîte à outils** en cliquant sur **Initialize LoadToolboxMembers VB** ou **Initialize LoadToolboxMembers CS** dans le menu **Outils**.  
  
6.  Générez l’application Windows en cliquant sur **Régénérer la solution** dans le menu **Générer**.  
  
7.  Exécutez l’application en cliquant sur **Démarrer le débogage** ou sur **Exécuter sans débogage**  dans le menu **Déboguer**.  
  
8.  Quand l’application s’exécute, cliquez sur l’un des contrôles que vous avez ajoutés à l’application.  
  
     Une boîte de message apparaît et affiche `"Hello world from Company.LoadToolboxMembers.Control1"` ou  `"Hello world from Company.LoadToolboxMembers.Control2"`.  
  
## Analyse de l’implémentation  
  
### Création de contrôles de boîte à outils  
 Les attributs assignés à `Control1` et `Control2` sont utilisées par la méthode `CreateItemList` au moment où elle interroge `Assembly` pour connaître les contrôles de **boîte à outils** disponibles.  
  
-   <xref:System.ComponentModel.ToolboxItemAttribute> exécute les deux fonctions suivantes :  
  
    -   Affectation de <xref:System.ComponentModel.ToolboxItemAttribute> à `Control1` et `Control2`, ce qui indique que chacun est un contrôle de boîte à outils.  
  
    -   Argument pour le constructeur <xref:System.ComponentModel.ToolboxItemAttribute>, qui indique si le <xref:System.Drawing.Design.ToolboxItem> par défaut ou une classe personnalisée dérivée de <xref:System.Drawing.Design.ToolboxItem> est utilisé quand le contrôle est ajouté à la **boîte à outils**.  
  
         L’instance de <xref:System.ComponentModel.ToolboxItemAttribute> qui est assignée à `Control1` est créée en utilisant un argument de `true`, ce qui indique qu’elle utilise une classe <xref:System.Drawing.Design.ToolboxItem> par défaut quand elle est ajoutée à la **boîte à outils**.  
  
         L’instance de <xref:System.ComponentModel.ToolboxItemAttribute> qui est assignée à `Control2` est créée en utilisant la classe <xref:System.Type> qui est dérivée de <xref:System.Drawing.Design.ToolboxItem>, `Control2_ToolboxItem`.  
  
-   La classe <xref:System.Drawing.ToolboxBitmapAttribute> spécifie les bitmaps utilisées par l’environnement pour identifier les contrôles.  
  
     Le fait d’incorporer une bitmap dans un assembly en définissant sa propriété **Action de génération** sur **Ressource incorporée** a pour effet de placer la bitmap dans l’espace de noms de l’assembly. Par conséquent, `Control1.bmp` peut être appelé `Company.LoadToolboxMembers.Control1.bmp`.  
  
     <xref:System.Drawing.ToolboxBitmapAttribute> prend en charge un constructeur qui utilise ce chemin complet comme argument. Par exemple, une classe <xref:System.Drawing.ToolboxBitmapAttribute> peut être appliquée à `Control1` en utilisant `[ToolboxBitmap("Company.LoadToolboxMembers.Control1.bmp")]`.  
  
     Par souci de flexibilité, cette procédure pas à pas utilise un constructeur qui prend une classe <xref:System.Type> comme premier argument du constructeur <xref:System.Drawing.ToolboxBitmapAttribute>. L’espace de noms servant à identifier le fichier bitmap est obtenu auprès de <xref:System.Type> puis inséré devant le nom de base de la bitmap.  
  
     Comme l’objet <xref:System.Type> chargé d’implémenter <xref:Microsoft.VisualStudio.Shell.Package>, `LoadToolboxMembers`, se trouve dans l’espace de noms `Company.LoadToolboxMembers`, `[ToolboxBitmap(typeof(Control1), "Control1.bmp")]` équivaut à `[ToolboxBitmap("Company.LoadToolboxMembers.Control1.bmp")]`.  
  
-   <xref:System.ComponentModel.DisplayNameAttribute> spécifie le nom du contrôle dans la **boîte à outils**.  
  
### Inscription d’un fournisseur de contrôles de boîte à outils  
 Le fait d’appliquer la classe <xref:Microsoft.VisualStudio.Shell.ProvideToolboxItemsAttribute> à la classe qui implémente <xref:Microsoft.VisualStudio.Shell.Package> a un effet sur les paramètres de Registre du VSPackage obtenu. Pour plus d’informations sur les paramètres de Registre d’un fournisseur <xref:System.Drawing.Design.ToolboxItem>, consultez [Inscription des fonctionnalités de prise en charge de boîte à outils](../misc/registering-toolbox-support-features.md).  
  
 L’environnement [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] utilise l’argument de version du constructeur <xref:Microsoft.VisualStudio.Shell.ProvideToolboxItemsAttribute> pour gérer la mise en cache des VSPackages qui fournissent les éléments à la **boîte à outils**. Une fois qu’un VSPackage a été chargé pour fournir des éléments de **boîte à outils**, une version mise en cache du VSPackage est utilisée tant que la version inscrite du fournisseur n’est pas modifiée. Par conséquent, si vous voulez modifier le produit de cette procédure pas à pas après l’avoir généré, veillez à modifier l’argument de version du constructeur <xref:Microsoft.VisualStudio.Shell.ProvideToolboxItemsAttribute> qui est appliqué à `AddToolboxItem`. Par exemple, `[ProvideToolboxItems(1)]` doit être remplacé par `[ProvideToolboxItems(2)]`. Si la version n’est pas modifiée, l’environnement [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] ne charge aucune des modifications apportées.  
  
 Dans cette procédure pas à pas, le VSPackage est configuré pour fournir uniquement des contrôles de **boîte à outils** qui prennent en charge le format de Presse\-papiers par défaut. Pour obtenir la liste des formats de Presse\-papiers par défaut, consultez [Extension de la boîte à outils](../misc/extending-the-toolbox.md). Si vous voulez prendre en charge d’autres formats de Presse\-papiers ou que vous décidez de ne pas prendre en charge un format par défaut, appliquez l’attribut <xref:Microsoft.VisualStudio.Shell.ProvideToolboxFormatAttribute> à la classe `LoadToolboxMembersPackage`. Pour plus d’informations sur l’inscription d’un fournisseur de contrôles de **boîte à outils**, consultez [Développement avancé de contrôles de boîte à outils](../misc/advanced-toolbox-control-development.md).  
  
### Ajout de contrôles à la boîte à outils  
 La fonctionnalité intégrée à `CreateItemList` assure l’émulation de ce qui est disponible dans <xref:System.Drawing.Design.ToolboxService.System%23Drawing%23Design%23IToolboxService%23GetToolboxItems%2A>.  
  
 La méthode `CreateItemList` examine uniquement les objets <xref:System.Type> non abstraits qui implémentent les interfaces <xref:System.ComponentModel.IComponent>.  
  
## Étapes suivantes  
 Le fait d’utiliser <xref:System.Drawing.Design.ToolboxService.System%23Drawing%23Design%23IToolboxService%23GetToolboxItems%2A> plutôt que `CreateItemList` améliorerait la robustesse du produit de cette procédure pas à pas.  
  
 Vous pouvez aussi modifier `CreateItemList` de façon à utiliser <xref:Microsoft.VisualStudio.Shell.Package.ParseToolboxResource%2A> pour charger les contrôles dans la **boîte à outils** selon une liste de texte incorporée dans l’assembly `LoadToolboxMembers`.  
  
## Voir aussi  
 [Extension de la boîte à outils](../misc/extending-the-toolbox.md)   
 [Inscription des fonctionnalités de prise en charge de boîte à outils](../misc/registering-toolbox-support-features.md)   
 [Développement avancé de contrôles de boîte à outils](../misc/advanced-toolbox-control-development.md)   
 [Procédures pas à pas de la Boîte à outils](../misc/toolbox-walkthroughs.md)
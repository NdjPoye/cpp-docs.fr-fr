---
title: "Cr&#233;ation d&#39;un consommateur simple | Microsoft Docs"
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
  - "consommateurs OLE DB, créer"
ms.assetid: ae32d657-72ea-4db8-9839-75cb5cff68ae
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Cr&#233;ation d&#39;un consommateur simple
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vous pouvez utiliser l'Assistant Projet ATL et l'Assistant Consommateur OLE DB pour générer un consommateur des modèles OLE DB.  
  
#### Pour créer une application console destinée à un consommateur OLE DB  
  
1.  Dans le menu **Fichier**, cliquez sur **Nouveau**, puis sur **Projet**.  
  
     La boîte de dialogue **Nouveau projet** s'affiche.  
  
2.  Dans le volet Types de projets, cliquez sur le dossier **Projets Visual C\+\+**, puis dans le volet Modèles, cliquez sur l'icône **Projet Win32**.  Dans la zone **Nom**, entrez un nom pour le projet, par exemple **MyCons**.  
  
3.  Cliquez sur **OK**.  
  
     L'Assistant Projet Win32 apparaît.  
  
4.  Dans la page **Paramètres de l'application**, sélectionnez **Application console**, puis sélectionnez **Ajouter la prise en charge de ATL**.  
  
5.  Cliquez sur **Terminer** pour fermer l'Assistant et générer le projet.  
  
 Ensuite, utilisez l'Assistant Consommateur OLE DB ATL pour ajouter un objet consommateur OLE DB.  
  
#### Pour créer un consommateur via l'Assistant Consommateur OLE DB ATL  
  
1.  Dans l'Affichage de classes, cliquez avec le bouton droit sur le projet `MyCons`.  
  
2.  Dans le menu contextuel, cliquez sur **Ajouter**, puis sur **Ajouter une classe**.  
  
     La boîte de dialogue **Ajouter une classe** s'affiche.  
  
3.  Dans le volet Catégories, cliquez sur le dossier **Visual C\+\+**, et dans le volet Modèles, cliquez sur l'icône **Consommateur OLE DB ATL**, puis cliquez sur **Ouvrir**.  
  
     L'Assistant Consommateur OLE DB ATL apparaît.  
  
4.  Cliquez sur le bouton **Source de données**.  
  
     La boîte de dialogue **Propriétés des liaisons de données** s'affiche.  
  
5.  Dans la boîte de dialogue **Propriétés des liaisons de données**, exécutez les tâches suivantes :  
  
    -   Sous l'onglet **Fournisseur**, spécifiez un fournisseur OLE DB  
  
    -   Sous l'onglet **Connexion**, spécifiez le nom du serveur, l'ID de connexion et le mot de passe de votre source de données, ainsi que la base de données sur le serveur  
  
    > [!NOTE]
    >  La fonctionnalité **Autoriser l'enregistrement du mot de passe** de la boîte de dialogue **Propriétés des liaisons de données** présente un problème de sécurité.  Dans **Entrez des informations pour vous connecter au serveur**, il y a deux cases d'option : **Utiliser la sécurité intégrée de Windows NT** et **Utiliser un nom d'utilisateur et un mot de passe spécifiques**.  
  
    > [!NOTE]
    >  Si vous sélectionnez **Utiliser un nom d'utilisateur et un mot de passe spécifiques**, vous avez la possibilité d'enregistrer le mot de passe \(à l'aide de la case à cocher **Autoriser l'enregistrement du mot de passe**\). Cependant, cette option n'est pas sécurisée.  Il est recommandé de sélectionner **Utiliser la sécurité intégrée de Windows NT**. Cette option utilise Windows NT pour vérifier votre identité.  
  
    > [!NOTE]
    >  Si vous ne pouvez pas utiliser la sécurité intégrée de Windows NT, utilisez une application intermédiaire pour demander à l'utilisateur le mot de passe, ou pour stocker le mot de passe à un emplacement sécurisé \(et non pas dans le code source\).  
  
     Après avoir sélectionné le fournisseur et effectué d'autres paramétrages, cliquez sur **Tester la connexion** afin de vérifier les sélections opérées dans les pages de boîtes de dialogue précédentes.  Si la zone **Résultats** indique « `Test connection succeeded` », cliquez sur **OK** pour créer la liaison de données.  
  
     La boîte de dialogue **Sélectionner l'objet de base de données** s'affiche.  
  
6.  Utilisez le contrôle d'arborescence pour sélectionner une table, une vue ou une procédure stockée.  Pour les besoins de cette procédure, sélectionnez la table Products dans la base de données Northwind.  
  
7.  Cliquez sur **OK**.  Vous retournez à l'Assistant Consommateur OLE DB ATL.  
  
8.  L'Assistant renseigne les noms pour les zones `Class` et **.h file** en fonction du nom de la table, de la vue ou de la procédure stockée que vous avez sélectionnée.  Vous pouvez modifier ces noms, le cas échéant.  
  
9. Désactivez la case à cocher **Avec attributs** pour que l'Assistant crée le code du consommateur à l'aide des [classes des modèles OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md) au lieu de l'option par défaut [Attributs du consommateur OLE DB](../../windows/ole-db-consumer-attributes.md).  
  
10. Sous **Type**, sélectionnez **Commande**.  
  
     L'Assistant crée un consommateur basé sur la classe [CCommand](../../data/oledb/ccommand-class.md) si vous sélectionnez **Commande**, ou un consommateur basé sur la classe [CTable](../../data/oledb/ctable-class.md) si vous sélectionnez **Table**.  La classe de table ou de commande est nommée selon l'objet sélectionné, mais vous pouvez modifier ce nom.  
  
11. Sous **Prendre en charge**, laissez les cases à cocher **Modifier**, **Insérer** et **Supprimer** désactivées.  
  
     Activez **Modifier**, **Insérer** et **Supprimer** pour prendre en charge la modification, l'insertion et la suppression des enregistrements du jeu de lignes, si nécessaire.  Pour plus d'informations sur l'enregistrement de données dans le magasin de données, consultez [Mise à jour des jeux de lignes](../../data/oledb/updating-rowsets.md).  
  
12. Cliquez sur **Terminer** pour créer le consommateur.  
  
 L'Assistant génère une classe d'enregistrement utilisateur et une classe de commande, comme indiqué dans [Classes de consommateur générées par l'Assistant](../../data/oledb/consumer-wizard-generated-classes.md).  La classe de commande prend le nom que vous avez entré dans la zone `Class` de l'Assistant \(dans le cas présent, `CProducts`\) et la classe d'enregistrement utilisateur prend un nom de la forme « *ClassName*Accessor » \(dans le cas présent, `CProductsAccessor`\).  
  
> [!NOTE]
>  L'Assistant met la ligne suivante dans Products.h :  
  
```  
#error Security Issue: The connection string may contain a password  
```  
  
> [!NOTE]
>  Cette ligne empêche l'application consommateur de compiler et vous rappelle de vérifier votre chaîne de connexion pour les mots de passe codés en dur.  Après avoir vérifié votre chaîne de connexion, vous pouvez supprimer cette ligne de code.  
  
## Voir aussi  
 [Création d'un consommateur OLE DB en utilisant l'Assistant](../../data/oledb/creating-an-ole-db-consumer-using-a-wizard.md)
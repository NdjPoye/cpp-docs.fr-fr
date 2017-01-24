---
title: "Insertion d&#39;un contr&#244;le sur une page Web (Didacticiel ATL, Partie&#160;7) | Microsoft Docs"
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
ms.assetid: 50dc4c95-c95b-4006-b88a-9826f7bdb222
caps.latest.revision: 15
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Insertion d&#39;un contr&#244;le sur une page Web (Didacticiel ATL, Partie&#160;7)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Votre contrôle est maintenant terminé.  Pour voir votre travail de contrôle dans une situation réelle, mettez\-le sur une page Web.  Un fichier HTML qui contient le contrôle a été créé lorsque vous avez défini votre contrôle.  Ouvrez le fichier PolyCtl.htm dans l'**Explorateur de solutions**, et vous pouvez voir votre contrôle sur une page Web.  
  
 Dans cette étape, vous créerez un script de la page Web pour répondre aux événements.  Vous allez modifier également le contrôle pour informer Internet Explorer que le contrôle est sûr pour les scripts.  
  
## Script de la page Web  
 Le contrôle est inactif pour le moment, par conséquent modifiez la page Web pour répondre aux événements que vous envoyez.  
  
#### Pour créer un script dans la page Web  
  
1.  Ouvrez PolyCtl.htm et sélectionnez le mode HTML.  Ajoutez les lignes suivantes au code HTML.  Elles doivent être ajoutées après `</OBJECT>` mais avant `</BODY>`.  
  
    ```  
  
    <SCRIPT LANGUAGE="VBScript">  
    <!--  
    Sub PolyCtl_ClickIn(x, y)  
       PolyCtl.Sides = PolyCtl.Sides + 1  
    End Sub  
    Sub PolyCtl_ClickOut(x, y)  
       PolyCtl.Sides = PolyCtl.Sides - 1  
    End Sub  
    -->  
    </SCRIPT>  
    ```  
  
2.  Enregistrez le fichier HTM.  
  
 Vous avez ajouté un code VBScript qui obtient la propriété Sides à partir du contrôle et augmente le nombre de côtés d'une unité si vous cliquez à l'intérieur du contrôle.  Si vous cliquez à l'extérieur du contrôle, vous réduisez le nombre de côtés d'un.  
  
## Indication que le contrôle est sécurisé pour le script  
 Vous pouvez afficher la page Web avec le contrôle dans Internet Explorer ou, plus commodément, utiliser la vue du navigateur Web intégré à Visual C\+\+.  Pour afficher votre contrôle dans la vue de navigateur Web, cliquez avec le bouton droit sur PolyCtl.htm, puis cliquez sur **Afficher dans le navigateur**.  
  
 Selon vos paramètres de sécurité Internet Explorer actuels, vous pouvez recevoir une boîte de dialogue d'alerte sécurité indiquant que le contrôle peut ne pas être sûr pour le script et causer des dommages.  Par exemple, si vous aviez un contrôle qui affichait un fichier mais également une méthode `Delete` qui supprimait un fichier, il est possible de l'afficher sur une page.  Toutefois, il n'est pas possible de créer un script, car un utilisateur peut appeler la méthode `Delete`.  
  
> [!IMPORTANT]
>  Pour ce didacticiel, vous pouvez modifier vos paramètres de sécurité dans Internet Explorer pour exécuter les contrôles ActiveX qui ne sont pas marqués comme sécurisés.  Dans le Panneau de configuration, cliquez sur **Propriétés Internet**, puis sur **Sécurité** pour modifier les paramètres appropriés.  Lorsque vous avez terminé le didacticiel, rétablissez les paramètres de sécurité à leur état d'origine.  
  
 Vous pouvez par programmation avertir Internet Explorer qu'il n'a besoin d'afficher la boîte de dialogue Alerte de sécurité pour ce contrôle.  Vous pouvez le faire avec l'interface `IObjectSafety` et ATL fournit une implémentation de cette interface dans la classe [IObjectSafetyImpl](../atl/reference/iobjectsafetyimpl-class.md).  Pour ajouter l'interface à votre contrôle, ajoutez `IObjectSafetyImpl` à votre liste des classes héritées et ajoutez une entrée pour celui\-ci dans votre mappage COM.  
  
#### Pour ajouter IObjectSafetyImpl au contrôle  
  
1.  Ajoutez la ligne suivante à la fin de la liste des classes héritées dans PolyCtl.h et ajoutez une virgule à la ligne précédente :  
  
     [!code-cpp[NVC_ATL_Windowing#62](../atl/codesnippet/CPP/putting-the-control-on-a-web-page-atl-tutorial-part-7_1.h)]  
  
2.  Ajoutez la ligne suivante au mappage COM dans PolyCtl.h :  
  
     [!code-cpp[NVC_ATL_Windowing#63](../atl/codesnippet/CPP/putting-the-control-on-a-web-page-atl-tutorial-part-7_2.h)]  
  
## Génération et test du contrôle  
 Génération du contrôle.  Une fois la génération terminée, rouvrez PolyCtl.htm dans la vue du navigateur.  Cette fois, la page Web doit être restituée directement sans boîte de dialogue d'alerte de sécurité.  Cliquez à l'intérieur du polygone ; le nombre de côtés augmente d'un.  Cliquez à l'extérieur du polygone pour réduire le nombre de côtés.  Si vous essayez de réduire le nombre de côtés en dessous de trois, vous obtenez le message d'erreur que vous avez défini.  
  
 [Revenir à l'étape 6](../atl/adding-a-property-page-atl-tutorial-part-6.md)  
  
## Étapes suivantes  
 Cela conclut le didacticiel ATL.  Pour obtenir des liens vers des informations supplémentaires sur ATL, consultez la [page de démarrage ATL](../atl/active-template-library-atl-concepts.md).  
  
## Voir aussi  
 [Didacticiel](../atl/active-template-library-atl-tutorial.md)
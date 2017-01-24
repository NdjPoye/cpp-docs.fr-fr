---
title: "Utilisation de la liaison de donn&#233;es RDO dans Visual&#160;C++ | Microsoft Docs"
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
  - "liaison de données (C++), RDO"
  - "RDO (C++), liaison de données"
  - "RemoteData (contrôle RDO), lier des données en Visual C++"
  - "RemoteData (contrôle), lier des données en Visual C++"
ms.assetid: 02b9cfe7-7bbe-4a01-b075-e28d9536ac4b
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Utilisation de la liaison de donn&#233;es RDO dans Visual&#160;C++
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Pour utiliser la liaison de données RDO dans Visual C\+\+, vous devez ajouter un contrôle RemoteData RDO et désigner une source de données ainsi qu'une source d'enregistrement \(requête SQL\).  Vous devez également ajouter un contrôle lié aux données RDO, le pointer vers un contrôle RemoteData RDO et sélectionner les champs à lier à la source d'enregistrement du contrôle RemoteData RDO.  
  
### Pour utiliser la liaison de données RDO dans Visual C\+\+  
  
1.  Configurez une [source de données ODBC](../../data/ado-rdo/odbc-connections.md), si ce n'est déjà fait.  
  
2.  Créez une application à boîtes de dialogue MFC ou une application Formview MFC par l'intermédiaire de l'Assistant Application MFC.  
  
3.  Ajoutez le contrôle Microsoft RemoteData \(contrôle RemoteData RDO\) à la boîte de dialogue ; consultez [Insertion du contrôle dans une application Visual C\+\+](../../data/ado-rdo/inserting-the-control-into-a-visual-cpp-application.md).  
  
4.  Pointez le contrôle RemoteData RDO vers la source de données ODBC.  
  
    1.  Cliquez avec le bouton droit sur le contrôle, puis cliquez sur **Propriétés**.  
  
    2.  Cliquez sur l'onglet **Contrôle**.  
  
    3.  Affectez **DataSource** à la source de données ODBC.  
  
    4.  Le cas échéant, définissez le nom d'utilisateur et le mot de passe de votre source de données ODBC.  Laissez en blanc si la source de données ne requiert ni nom d'utilisateur ni mot de passe.  
  
    5.  Entrez une requête SQL dans la propriété **SQL**.  Les contrôles liés aux données peuvent se lier aux résultats de cette requête.  
  
5.  Définissez d'autres propriétés du contrôle RemoteData RDO, si nécessaire.  
  
6.  Ajoutez un contrôle lié aux données.  Par exemple, ajoutez le **contrôle DBGrid** et définissez la source de données de la façon suivante.  
  
    1.  Cliquez avec le bouton droit sur le DBGrid, puis cliquez sur **Propriétés**.  
  
    2.  Cliquez sur l'onglet **Tout**.  
  
    3.  Affectez la propriété **DataSource** au contrôle RemoteData RDO.  Cliquez sur la zone de liste déroulante modifiable de la propriété et recherchez l'identificateur du contrôle RemoteData RDO.  L'identificateur par défaut est IDC\_REMOTEDATACTL1.  
  
7.  Pour exécuter en mode test, utilisez CTRL\+T.  Vous pouvez faire défiler les données.  Appuyez sur la touche Échap ou fermez la boîte de dialogue pour mettre fin au mode test.  
  
 Si vous compilez et exécutez le programme, vous pouvez également faire défiler les données.  
  
## Voir aussi  
 [Liaison de données RDO](../../data/ado-rdo/rdo-databinding.md)   
 [Liaison de données avec des contrôles ActiveX dans Visual C\+\+](../../data/ado-rdo/databinding-with-activex-controls-in-visual-cpp.md)
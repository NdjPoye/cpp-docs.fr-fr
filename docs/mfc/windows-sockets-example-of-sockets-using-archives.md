---
title: "Windows Sockets&#160;: exemple de sockets utilisant des archives | Microsoft Docs"
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
  - "exemples (MFC), Windows Sockets"
  - "sockets (C++), avec archives"
  - "Windows Sockets (C++), avec archives"
ms.assetid: 2e3c9bb2-7e7b-4f28-8dc5-6cb7a484edac
caps.latest.revision: 12
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Windows Sockets&#160;: exemple de sockets utilisant des archives
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article présente un exemple d'utilisation de la classe [CSocket](../mfc/reference/csocket-class.md).  L'exemple utilise des objets d' `CArchive` pour sérialiser des données via un socket.  Notez qu'il n'est pas sérialisation de document à partir d'un fichier.  
  
 L'exemple suivant montre comment vous utilisez l'archive à envoyer et recevoir des données via des objets d' `CSocket`.  Cet exemple est conçu pour que deux instances de cette application \(sur le même ordinateur ou sur des ordinateurs différents du réseau\) échangent des données.  Une instance envoie les données, que l'autre instance reçoit et accuse réception.  L'une ou l'autre application peut initialiser un échange, et l'une ou l'autre peut jouer le rôle de serveur ou de client à une autre application.  La fonction suivante est définie dans la classe d'affichage de l'application :  
  
 [!code-cpp[NVC_MFCSimpleSocket#1](../mfc/codesnippet/CPP/windows-sockets-example-of-sockets-using-archives_1.cpp)]  
  
 La chose la plus importante sur cet exemple est que sa structure est analogue à celui d'un MFC `Serialize` .  La fonction membre du **PacketSerialize** se compose d'une instruction d' **if** avec une clause de **else**.  La fonction reçoit deux références d' [CArchive](../mfc/reference/carchive-class.md) comme paramètres : `arData` et `arAck`.  Si l'objet d'archive `arData` est défini pour la journalisation \(émission\), la branche d' **if** s'exécute; sinon, si `arData` est défini pour le chargement \(recevoir\) la fonction prend le branchement de **else**.  Pour plus d'informations sur la sérialisation en MFC, consultez [Serialisation](../mfc/how-to-make-a-type-safe-collection.md).  
  
> [!NOTE]
>  L'objet d'archive de `arAck` est supposé être l'inverse de `arData`.  Si `arData` est pour envoi, `arAck` le reçoit, et l'inverse est vrai.  
  
 Pour envoi, la fonction d'exemple boucle pour un nombre spécifié de fois, générant chaque fois des données aléatoires à des fins de démonstration.  Votre application bénéficie des données réelles d'une certaine source, tel qu'un fichier.  L'opérateur d'insertion de l'archivage d' `arData` \(**\<\<**\) permet d'envoyer un flux de trois segments successifs de données:  
  
-   Une « en\-tête » qui spécifie la nature des données \(dans ce cas, la valeur de la variable d' `bValue` et le nombre de copies sont envoyées\).  
  
     Les deux éléments sont générés de façon aléatoire pour cet exemple.  
  
-   Le nombre de copies des données spécifiées.  
  
     La boucle interne de **pour** envoie `bValue` le nombre de fois spécifié.  
  
-   Une chaîne appelée `strText` que le récepteur affiche à son l'utilisateur.  
  
 Pour reception, la fonction opère de façon similaire, sauf qu'elle utilise l'opérateur d'extraction d'archive \(**\>\>**\) pour extraire les données de l'archive.  L'application de destination vérifie les données qu'elle reçoit, affiche le message final « Reçu », puis renvoie en retour un message indiquant « Envoyé » pour l'application émettrice à afficher.  
  
 Dans ce modèle de communications, le mot « Reçu », le message envoyé dans la variable de `strText` est à afficher à l'autre bout de la communication, de sorte à indiquer à l'utilisateur récepteur qu'un certain nombre de paquets de données ont été reçus.  Le destinataire répond avec une chaîne similaire qui indique « Envoyé », pour affichage sur l'écran initial de l'expéditeur.  La réception des deux chaînes indique que la communication réussie s'est produite.  
  
> [!CAUTION]
>  Si vous écrivez un programme client MFC pour communiquer avec des serveurs \(non\-MFC\) établis, n'envoyez pas les objets C\+\+ à travers l'archive.  Sauf si le serveur est une application de MFC qui comprend les types d'objets que vous souhaitez envoyer, il ne peut pas recevoir et désérialiser vos objets.  Un exemple dans l'article [Protocole Windows : Ordre d'octet](../mfc/windows-sockets-byte-ordering.md) indique une communication de ce type.  
  
 Pour plus d'informations, consultez la spécification Windows Sockets : **htonl**, **htons**, **ntohl**, **ntohs**.  De même, pour plus d'informations, consultez:  
  
-   [Windows Sockets : dérivation à partir des classes de sockets](../mfc/windows-sockets-deriving-from-socket-classes.md)  
  
-   [Windows Sockets : fonctionnement des sockets avec des archives](../mfc/windows-sockets-how-sockets-with-archives-work.md)  
  
-   [Windows Sockets : arrière\-plan](../mfc/windows-sockets-background.md)  
  
## Voir aussi  
 [Windows Sockets dans MFC](../mfc/windows-sockets-in-mfc.md)   
 [CArchive::IsStoring](../Topic/CArchive::IsStoring.md)   
 [CArchive::operator \<\<](../Topic/CArchive::operator%20%3C%3C.md)   
 [CArchive::operator \>\>](../Topic/CArchive::operator%20%3E%3E.md)   
 [CArchive::Flush](../Topic/CArchive::Flush.md)   
 [CObject::Serialize](../Topic/CObject::Serialize.md)
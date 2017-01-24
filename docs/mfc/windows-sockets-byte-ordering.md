---
title: "Windows Sockets&#160;: classement des octets | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "problèmes d'ordre d'octet dans la programmation de sockets"
  - "sockets (C++), problèmes d'ordre d'octet"
  - "Windows Sockets (C++), problèmes d'ordre d'octet"
ms.assetid: 8a787a65-f9f4-4002-a02f-ac25a5dace5d
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Windows Sockets&#160;: classement des octets
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article et deux autres expliquent plusieurs problèmes de programmation Windows Sockets.  Cet article couvre le classement d'octet.  Les autres problèmes sont traitées dans les articles : [Protocole Windows : Blocage](../mfc/windows-sockets-blocking.md) et [Protocole Windows : La conversion de chaînes](../mfc/windows-sockets-converting-strings.md).  
  
 Si vous utilisez ou dérivez de la classe [CAsyncSocket](../mfc/reference/casyncsocket-class.md), vous devez gérer ces problèmes vous\-même.  Si vous utilisez ou dérivez de la classe [CSocket](../mfc/reference/csocket-class.md), MFC les gère automatiquement.  
  
## Ordre d'octet  
 L'ordre d'octet utilisé pour le stockage des données varie parfois en fonction de l'architecture de la machine.  Par exemple, les ordinateurs basé sur Intel stockent les données dans l'ordre inverse des ordinateurs de Macintosh \(Motorola\).  La marque d'ordre d'octet Intel, appelée « little\-endian », est également l'inverse de l'ordre « avec primauté des octets de poids fort » du réseau standard.  Le tableau suivant décrit ces termes.  
  
### Classement des bites avec primauté des octets de poids faible et avec primauté des octets de poids fort \(little\-endian et big\-endian\)  
  
|Ordre d'octet|Signification|  
|-------------------|-------------------|  
|Avec primauté des octets de poids fort \(big\-endian\)|L'octet le plus significatif figure à l'extrémité gauche d'un mot,|  
|Avec primauté des octets de poids faible \(little\-endian\)|L'octet le plus significatif figure à l'extrémité droite d'un mot.|  
  
 Généralement, vous n'avez pas à vous soucier de l'ordre des octets de la conversion pour les données que vous devez envoyer et recevoir sur le réseau, mais il y a des situations dans lesquelles vous devez convertir des ordres d'octets.  
  
## Lorsque vous devez convertir des ordres d'octet  
 Vous devez convertir des ordres d'octets dans les situations suivantes :  
  
-   Vous transmettez les informations qui doivent être interprétées par le réseau, par opposition aux données que vous envoyez à un autre ordinateur.  Par exemple, vous pouvez passer les ports et les adresses, ce que le réseau doit comprendre.  
  
-   L'application serveur avec laquelle vous communiquez n'est pas une application de MFC \(et vous n'avez pas le code source de celle\-ci\).  Ceci appelle des conversions d'ordre d'octet si les deux ordinateurs ne partagent pas le même ordre d'octet.  
  
## Lorsque vous ne devez pas convertir des ordres d'octet  
 Vous pouvez éviter le travail de convertir les ordres d'octets dans les situations suivantes :  
  
-   Les ordinateurs à chaque extrémité peuvent accepter de ne pas échanger des octets, et les deux ordinateurs utilisent le même ordre d'octets.  
  
-   Le serveur avec lequel vous communiquez est une application de MFC.  
  
-   Vous avez le code source du serveur avec lequel vous communiquez avec, vous pouvez indiquer explicitement si vous devez convertir des ordres d'octet ou non.  
  
-   Vous pouvez déplacer le serveur en MFC.  Il est relativement facile d'effectuer les opérations, et le résultat est généralement un code plus court et plus rapide.  
  
 En travaillant avec [CAsyncSocket](../mfc/reference/casyncsocket-class.md), vous devez gérer toutes les conversions nécessaires de d'ordre d'octet vous\-même.  Windows Sockets normalise le modèle « avec primauté des octets de poids fort » d'ordre d'octet et fournit des fonctions pour convertir des données entre cette commande et d'autres.  [CArchive](../mfc/reference/carchive-class.md), toutefois, que vous utilisez avec [CSocket](../mfc/reference/csocket-class.md), utilise l'ordre inverse \(« little\-endian »\), mais `CArchive` prend soin des détails sur les conversions d'ordre d'octet pour vous.  À l'aide de cette norme de classement dans vos applications, ou de l'utilisation de fonctions de conversion d'ordre d'octet Windows Sockets, vous pouvez rendre votre code plus portable.  
  
 Le cas idéal pour utiliser MFC sockets est lorsque vous écrivez les deux extrémités de la communication : utilisant MFC aux deux extrémités.  Si vous écrivez une application qui communique avec les applications non\-MFC, telles qu'un serveur FTP, vous devrez probablement gérer l'échange d'octets vous\-même avant que vous passiez les données à l'objet archive, à l'aide des routines de conversion de Windows \( **ntohs**, **ntohl**, **htons**, et **htonl**.  Un exemple de ces fonctions utilisées dans les communications avec une application non\-MFC apparaît plus loin dans cet article.  
  
> [!NOTE]
>  Lorsque l'autre extrémité de la communication n'est pas une application de MFC, vous devez également éviter de transmettre en continu des objets C\+\+ dérivés de `CObject` dans votre archive car le récepteur ne peut pas les gérer.  Consultez la remarque rattachée à [Protocole Windows : Utiliser des sockets avec des archives](../mfc/windows-sockets-using-sockets-with-archives.md).  
  
 Pour plus d'informations sur les ordres d'octets, consultez la spécification de Windows Socket, disponible dans [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
## Un exemple de conversion d'ordre d'octet  
 L'exemple suivant illustre une fonction de sérialisation pour un objet `CSocket` qui utilise une archive.  Il illustre également l'utilisation des fonctions de conversion d'ordre d'octet dans l'API de chiffrement Windows.  
  
 Cet exemple présente un scénario dans lequel vous écrivez un client qui communique avec une application serveur non\-MFC pour laquelle vous ne mettez pas d'accès au code source.  Dans ce scénario, vous devez supposer que le serveur non\-MFC utilise l'ordre d'octets du réseau standard.  En revanche, votre application cliente MFC utilise un objet `CArchive` avec un objet `CSocket`, et `CArchive` utilise l'ordre d'octet « little\-endian », l'inverse de la norme réseau.  
  
 Supposons que le serveur non\-MFC avec lequel vous envisagez de communiquer un protocole établi pour un paquet de message comme les éléments suivants :  
  
 [!code-cpp[NVC_MFCSimpleSocket#5](../mfc/codesnippet/CPP/windows-sockets-byte-ordering_1.cpp)]  
  
 En termes de MFC, cela est exprimé comme suit :  
  
 [!code-cpp[NVC_MFCSimpleSocket#6](../mfc/codesnippet/CPP/windows-sockets-byte-ordering_2.cpp)]  
  
 En C\+\+, un `struct` est essentiellement la même chose en tant que classe.  La structure de `Message` peut avoir des méthodes, telles que la méthode `Serialize` déclarée ci\-dessus.  La fonction membre `Serialize` peut se présenter comme suit :  
  
 [!code-cpp[NVC_MFCSimpleSocket#7](../mfc/codesnippet/CPP/windows-sockets-byte-ordering_3.cpp)]  
  
 Cet exemple appelle les conversions d'ordre d'octets de données parce qu'il y a une incompatibilité claire entre l'ordre des octets de l'application serveur non\-MFC d'un côté et le `CArchive` utilisé dans votre application cliente MFC de l'autre.  L'exemple illustre plusieurs fonctions de conversion d'ordre d'octet que Windows Sockets fournit.  Le tableau suivant décrit ces fonctions.  
  
### Fonctions de conversion de marque d'ordre d'octet de Windows Sockets  
  
|Fonction|Objectif|  
|--------------|--------------|  
|**ntohs**|Convertir une valeur 16 bits de l'ordre d'octets du réseau qui héberge la marque d'ordre d'octet \(avec primauté des octets de poids fort à little\-endian.\)|  
|**ntohl**|Convertir une valeur 32 bits de l'ordre d'octets du réseau qui héberge l'ordre d'octet \(avec primauté des octets de poids fort à little\-endian.\)|  
|**Htons**|Convertir une valeur 16 bits de l'ordre d'octets hôte du réseau qui héberge l'ordre d'octet \(avec primauté des octets de poids faible jusqu'à big\-endian.\)|  
|**Htonl**|Convertir une valeur 32 bits de l'ordre d'octets hôte du réseau qui héberge l'ordre d'octet \(de little\-endian à big\-endian.\)|  
  
 Un autre point de cet exemple est que lorsque l'application de socket à l'autre extrémité de la communication est une application non\-MFC, vous devez éviter d'effectuer une opération comme ce qui suit :  
  
 `ar << pMsg;`  
  
 où `pMsg` est un pointeur vers l'objet C\+\+ actuel dérivé de la classe `CObject`.  Ceci enverra les informations supplémentaires MFC associées aux objets et le serveur ne les comprendra pas, tel qu'il le ferait s'il s'agissait d'une application MFC.  
  
 Pour plus d'informations, consultez :  
  
-   [Windows Sockets : utilisation de la classe CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows Sockets : Arrière\-plan](../mfc/windows-sockets-background.md)  
  
-   [Windows Sockets : Flux Sockets](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows Sockets : Datagramme Sockets](../mfc/windows-sockets-datagram-sockets.md)  
  
## Voir aussi  
 [Windows Sockets dans MFC](../mfc/windows-sockets-in-mfc.md)
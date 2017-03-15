---
title: "Blocs de messages asynchrones | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "jointure non gourmande (runtime d'accès concurrentiel)"
  - "blocs de messages asynchrones"
  - "jointure gourmande (runtime d'accès concurrentiel)"
ms.assetid: 79c456c0-1692-480c-bb67-98f2434c1252
caps.latest.revision: 36
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 36
---
# Blocs de messages asynchrones
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La bibliothèque d’Agents fournit plusieurs types de blocs de messages qui vous permettent de propager des messages entre les composants d’application de manière thread-safe. Ces types de blocs de messages sont souvent utilisés avec les différentes routines de passage de messages, tel que [concurrency::send](../Topic/send%20Function.md), [concurrency::asend](../Topic/asend%20Function.md), [concurrency::receive](../Topic/receive%20Function.md), et [concurrency::try_receive](../Topic/try_receive%20Function.md). Pour plus d’informations sur le message passant des routines qui sont définies par la bibliothèque d’Agents, consultez [Message Passing Functions](../../parallel/concrt/message-passing-functions.md).  
  
##  <a name="a-nametopa-sections"></a><a name="top"></a> Sections  
 Cette rubrique contient les sections suivantes :  
  
- [Sources et cibles](#sources_and_targets)  
  
- [Propagation de messages](#propagation)  
  
- [Vue d’ensemble des Types de bloc de Message](#overview)  
  
- [Classe unbounded_buffer](#unbounded_buffer)  
  
- [Classe overwrite_buffer](#overwrite_buffer)  
  
- [Classe single_assignment](#single_assignment)  
  
- [Call, classe](#call)  
  
- [Classe transformer](#transformer)  
  
- [Classe Choice](#choice)  
  
- [Classes de jointure et multitype_join](#join)  
  
- [Classe Timer](#timer)  
  
- [Filtrage des messages](#filtering)  
  
- [Réservation de messages](#reservation)  
  
##  <a name="a-namesourcesandtargetsa-sources-and-targets"></a><a name="sources_and_targets"></a> Sources et cibles  
 Sources et cibles sont deux participants importants au passage de message. Un *source* fait référence à un point de terminaison de communication qui envoie des messages. Un *cible* fait référence à un point de terminaison de communication qui reçoit des messages. Vous pouvez considérer une source comme un point de terminaison que vous lisez à partir d’et une cible comme un point de terminaison que vous écrivez à. Connectent des applications sources et cibles ensemble pour former *réseaux de messagerie*.  
  
 La bibliothèque d’Agents utilise deux classes abstraites pour représenter les sources et cibles : [concurrency::ISource](../../parallel/concrt/reference/isource-class.md) et [concurrency::ITarget](../../parallel/concrt/reference/itarget-class.md). Les types de blocs de message qui agissent comme sources dérivent `ISource`; les types de blocs de message qui agissent comme cibles dérivent `ITarget`. Types de bloc de message qui agissent en tant que sources et cibles dérivent `ISource` et `ITarget`.  
  
 [[Haut](#top)]  
  
##  <a name="a-namepropagationa-message-propagation"></a><a name="propagation"></a> Propagation de messages  
 *La propagation des messages* consiste à envoyer un message à partir d’un composant vers un autre. Lorsqu’un bloc de message reçoit un message, il peut accepter, refuser ou reporter. Chaque type de bloc de message stocke et transmet des messages de différentes manières. Par exemple, la `unbounded_buffer` classe stocke un nombre illimité de messages, la `overwrite_buffer` classe stocke un seul message à la fois, et la classe transformer stocke une version modifiée de chaque message. Ces types de blocs de messages sont décrits plus en détail plus loin dans ce document.  
  
 Lorsqu’un bloc de message accepte un message, il peut éventuellement effectuer le travail et, si le bloc de message est une source, passer le message résultant à un autre membre du réseau. Un bloc de message peut utiliser une fonction de filtre pour refuser les messages qu’il ne souhaite pas recevoir. Les filtres sont décrits plus en détail plus loin dans cette rubrique, dans la section [filtrage des messages](#filtering). Un bloc de message qui reporte un message peut réserver ce message et l’utiliser ultérieurement. La réservation de messages est décrite plus en détail plus loin dans cette rubrique, dans la section [la réservation de messages](#reservation).  
  
 La bibliothèque d’Agents permet aux blocs de messages de façon asynchrone ou synchrone transmettre des messages. Lorsque vous passez un message à un bloc de message de façon synchrone, par exemple, à l’aide de la `send` (fonction), le runtime bloque le contexte actuel jusqu'à ce que le bloc cible accepte ou rejette le message. Lorsque vous passez un message à un bloc de message asynchrone, par exemple, à l’aide de la `asend` (fonction), le runtime propose le message à la cible, et si la cible accepte le message, le runtime planifie une tâche asynchrone qui propage le message au récepteur. Le runtime utilise des tâches légères pour propager des messages de manière coopérative. Pour plus d’informations sur les tâches légères, consultez [le Planificateur de tâches](../../parallel/concrt/task-scheduler-concurrency-runtime.md).  
  
 Applications interconnecter sources et cibles pour les réseaux de messagerie de formulaire. En règle générale, vous liez le réseau et appelez `send` ou `asend` pour passer des données au réseau. Pour vous connecter à un bloc de message source vers une cible, appelez le [Concurrency::ISource :: link_target](../Topic/ISource::link_target%20Method.md) méthode. Pour déconnecter un bloc source à partir d’une cible, appelez le [Concurrency::ISource :: unlink_target](../Topic/ISource::unlink_target%20Method.md) méthode. Pour déconnecter un bloc source de toutes ses cibles, appelez le [Concurrency::ISource :: unlink_targets](../Topic/ISource::unlink_targets%20Method.md) méthode. Lorsqu’un des types de bloc de message prédéfinis quitte la portée ou est détruit, il se déconnecte automatiquement à partir de tous les blocs cibles. Certains types de bloc de message limitent le nombre maximal de cibles auxquelles ils peuvent écrire à. La section suivante décrit les restrictions qui s’appliquent aux types de bloc de message prédéfinis.  
  
 [[Haut](#top)]  
  
##  <a name="a-nameoverviewa-overview-of-message-block-types"></a><a name="overview"></a> Vue d’ensemble des Types de bloc de Message  
 Le tableau suivant décrit brièvement le rôle des types de blocs de messages importants.  
  
 [unbounded_buffer](#unbounded_buffer)  
 Stocke une file d’attente de messages.  
  
 [overwrite_buffer](#overwrite_buffer)  
 Stocke un message qui peut être écrit dans et à partir de plusieurs fois.  
  
 [single_assignment](#single_assignment)  
 Stocke un message qui peut être écrit une seule fois et lues plusieurs fois.  
  
 [appel](#call)  
 Effectue un travail lorsqu’il reçoit un message.  
  
 [classe transformer](#transformer)  
 Effectue un travail lorsqu’il reçoit des données et envoie le résultat de ce travail à un autre bloc cible. La `transformer` classe peut agir sur différents types d’entrées et sortie.  
  
 [choix](#choice)  
 Sélectionne le premier message disponible dans un jeu de sources.  
  
 [jointure et jointure multitype](#join)  
 Attendez que tous les messages à être reçus à partir d’un ensemble de sources et ensuite combiner les messages dans un message pour un autre bloc de message.  
  
 [minuteur](#timer)  
 Envoie un message à un bloc cible à intervalles réguliers.  
  
 Ces types de blocs de messages ont des caractéristiques différentes qui les rendent utiles pour différentes situations. Voici quelques-unes des caractéristiques :  
  
- *Type de propagation*: indique si le bloc de message agit comme une source de données, de récepteur de données ou les deux.  
  
- *Classement des messages*: indique si le bloc de message conserve l’ordre d’origine dans lequel les messages sont envoyés ou reçus. Chaque type de bloc de message prédéfini conserve l’ordre d’origine dans lequel il envoie ou reçoit des messages.  
  
- *Nombre de source*: le nombre maximal de sources de lecture depuis le bloc de message.  
  
- *Nombre de cibler*: le nombre maximal de cibles que le bloc de message peut écrire.  
  
 Le tableau suivant montre comment ces caractéristiques concernent les différents types de blocs de messages.  
  
|Type de bloc de message|Type de propagation (Source, cible ou les deux)|Message de commande (ordonné ou non ordonné)|Nombre de sources|Nombre de cibles|  
|------------------------|--------------------------------------------------|-----------------------------------------------|------------------|------------------|  
|`unbounded_buffer`|Both|Ordered|Illimitée|Illimitée|  
|`overwrite_buffer`|Both|Ordered|Illimitée|Illimitée|  
|`single_assignment`|Both|Ordered|Illimitée|Illimitée|  
|`call`|Target|Ordered|Illimitée|Non applicable|  
|`transformer`|Both|Ordered|Illimitée|1|  
|`choice`|Both|Ordered|10|1|  
|`join`|Both|Ordered|Illimitée|1|  
|`multitype_join`|Both|Ordered|10|1|  
|`timer`|Source|Non applicable|Non applicable|1|  
  
 Les sections suivantes décrivent les types de bloc de message plus en détail.  
  
 [[Haut](#top)]  
  
##  <a name="a-nameunboundedbuffera-unboundedbuffer-class"></a><a name="unbounded_buffer"></a> Classe unbounded_buffer  
 Le [concurrency::unbounded_buffer](../Topic/unbounded_buffer%20Class.md) classe représente une structure de messagerie asynchrone à usage général. Cette classe stocke une file d'attente de messages de type premier entré, premier sorti (FIFO). Plusieurs cibles peuvent lire ces messages et plusieurs sources peuvent y écrire. Quand une cible reçoit un message d’un `unbounded_buffer` de l’objet, ce message est supprimé de la file d’attente. Par conséquent, bien qu’un `unbounded_buffer` objet peut avoir plusieurs cibles, qu’une seule cible reçoit chaque message. La classe `unbounded_buffer` est utile quand vous voulez transmettre plusieurs messages à un autre composant et que ce composant doit recevoir chaque message.  
  
### <a name="example"></a>Exemple  
 L’exemple suivant montre la structure de base de l’utilisation avec la `unbounded_buffer` classe. Cet exemple envoie trois valeurs à un `unbounded_buffer` de l’objet, puis le lit ces valeurs à partir du même objet.  
  
 [!code-cpp[concrt-unbounded_buffer-structure#1](../../parallel/concrt/codesnippet/CPP/asynchronous-message-blocks_1.cpp)]  
  
 Cet exemple génère la sortie suivante :  
  
```Output  
334455  
```  
  
 Pour un exemple complet qui montre comment utiliser le `unbounded_buffer` de classe, consultez la page [Comment : implémenter divers modèles de producteur-consommateur](../../parallel/concrt/how-to-implement-various-producer-consumer-patterns.md).  
  
 [[Haut](#top)]  
  
##  <a name="a-nameoverwritebuffera-overwritebuffer-class"></a><a name="overwrite_buffer"></a> Classe overwrite_buffer  
 Le [concurrency::overwrite_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md) ressemble à la `unbounded_buffer` classe, à ceci près qu’un `overwrite_buffer` objet stocke seulement un message. En outre, lorsqu’une cible reçoit un message d’un `overwrite_buffer` de l’objet, ce message n’est pas supprimé de la mémoire tampon. Par conséquent, plusieurs cibles reçoivent une copie du message.  
  
 La `overwrite_buffer` classe est utile lorsque vous voulez passer plusieurs messages à un autre composant, mais que ce composant nécessite uniquement la valeur la plus récente. Cette classe est également utile quand vous voulez diffuser un message vers plusieurs composants.  
  
### <a name="example"></a>Exemple  
 L’exemple suivant montre la structure de base de l’utilisation avec la `overwrite_buffer` classe. Cet exemple envoie trois valeurs à un `overwrite _buffer` de l’objet, puis lit la valeur actuelle du même objet trois fois. Cet exemple est similaire à l’exemple de la `unbounded_buffer` classe. Toutefois, la `overwrite_buffer` classe stocke seulement un message. En outre, le runtime ne supprime pas le message d’une `overwrite_buffer` de l’objet après qu’il est lu.  
  
 [!code-cpp[concrt-overwrite_buffer-structure#1](../../parallel/concrt/codesnippet/CPP/asynchronous-message-blocks_2.cpp)]  
  
 Cet exemple génère la sortie suivante :  
  
```Output  
555555  
```  
  
 Pour un exemple complet qui montre comment utiliser le `overwrite_buffer` de classe, consultez la page [Comment : implémenter divers modèles de producteur-consommateur](../../parallel/concrt/how-to-implement-various-producer-consumer-patterns.md).  
  
 [[Haut](#top)]  
  
##  <a name="a-namesingleassignmenta-singleassignment-class"></a><a name="single_assignment"></a> Classe single_assignment  
 Le [concurrency::single_assignment](../../parallel/concrt/reference/single-assignment-class.md) ressemble à la `overwrite_buffer` classe, à ceci près qu’un `single_assignment` objet peut être écrites dans une seule fois. Comme pour la classe `overwrite_buffer`, quand une cible reçoit un message d'un objet `single_assignment`, le message n'est pas supprimé de l'objet. Par conséquent, plusieurs cibles reçoivent une copie du message. La `single_assignment` classe est utile lorsque vous voulez diffuser un message à plusieurs composants.  
  
### <a name="example"></a>Exemple  
 L’exemple suivant montre la structure de base de l’utilisation avec la `single_assignment` classe. Cet exemple envoie trois valeurs à un `single_assignment` de l’objet, puis lit la valeur actuelle du même objet trois fois. Cet exemple est similaire à l’exemple de la `overwrite_buffer` classe. Bien qu’à la fois les `overwrite_buffer` et `single_assignment` classes de stocker un seul message, la `single_assignment` classe peut être écrites une seule fois.  
  
 [!code-cpp[concrt-single_assignment-structure#1](../../parallel/concrt/codesnippet/CPP/asynchronous-message-blocks_3.cpp)]  
  
 Cet exemple génère la sortie suivante :  
  
```Output  
333333  
```  
  
 Pour un exemple complet qui montre comment utiliser le `single_assignment` de classe, consultez [procédure pas à pas : mise en œuvre des perspectives](../../parallel/concrt/walkthrough-implementing-futures.md).  
  
 [[Haut](#top)]  
  
##  <a name="a-namecalla-call-class"></a><a name="call"></a> Call, classe  
 Le [concurrency::call](../../parallel/concrt/reference/call-class.md) classe agit comme un récepteur de message qui exécute une fonction de travail lorsqu’il reçoit des données. Cette fonction de travail peut être une expression lambda, un objet de fonction ou un pointeur de fonction. Un `call` objet se comporte différemment d’un appel de fonction ordinaire car il agit en parallèle à d’autres composants qui envoient des messages. Si un `call` objet exécute un travail lorsqu’il reçoit un message, il ajoute ce message à une file d’attente. Chaque `call` processus de l’objet file d’attente de messages dans l’ordre dans lequel ils sont reçus.  
  
### <a name="example"></a>Exemple  
 L’exemple suivant montre la structure de base de l’utilisation avec la `call` classe. Cet exemple crée un `call` objet imprime chaque valeur qu’il reçoit dans la console. Puis, l’exemple envoie trois valeurs à la `call` objet. Étant donné que le `call` objet traite les messages sur un thread séparé, cet exemple utilise également une variable de compteur et une [événement](../../parallel/concrt/reference/event-class.md) objet pour vous assurer que le `call` objet traite tous les messages avant le `wmain` fonction renvoie.  
  
 [!code-cpp[concrt-call-structure#1](../../parallel/concrt/codesnippet/CPP/asynchronous-message-blocks_4.cpp)]  
  
 Cet exemple génère la sortie suivante :  
  
```Output  
334455  
```  
  
 Pour un exemple complet qui montre comment utiliser le `call` de classe, consultez la page [Comment : fournir des fonctions de travail aux Classes call et transformer](../../parallel/concrt/how-to-provide-work-functions-to-the-call-and-transformer-classes.md).  
  
 [[Haut](#top)]  
  
##  <a name="a-nametransformera-transformer-class"></a><a name="transformer"></a> Classe transformer  
 Le [concurrency::transformer](../../parallel/concrt/reference/transformer-class.md) classe agit comme un destinataire du message et un expéditeur de message. Le `transformer` ressemble à la `call` classe, car elle exécute une fonction de travail définie par l’utilisateur lorsqu’il reçoit des données. Toutefois, la `transformer` classe envoie également le résultat de la fonction de travail à des objets de destinataire. Comme un `call` objet, un `transformer` objet agit en parallèle à d’autres composants qui envoient des messages. Si un `transformer` objet exécute un travail lorsqu’il reçoit un message, il ajoute ce message à une file d’attente. Chaque `transformer` objet traite ses messages en file d’attente dans l’ordre dans lequel ils sont reçus.  
  
 La `transformer` classe envoie son message à une cible. Si vous définissez la `_PTarget` paramètre dans le constructeur `NULL`, vous pouvez spécifier ultérieurement la cible en appelant le [concurrency::link_target](../Topic/source_block::link_target%20Method.md) (méthode).  
  
 Contrairement à tous les autres types de blocs de messages asynchrones fournis par la bibliothèque d’Agents, le `transformer` classe peut agir sur différents types d’entrées et sortie. Cette capacité à transformer des données d’un type en un autre fait la `transformer` classe un composant clé dans de nombreux réseaux simultanés. En outre, vous pouvez ajouter plus de fonctionnalités parallèles affinées dans la fonction de travail d’un `transformer` objet.  
  
### <a name="example"></a>Exemple  
 L’exemple suivant montre la structure de base de l’utilisation avec la `transformer` classe. Cet exemple crée un `transformer` que multiplie chaque entrée de l’objet `int` valeur par 0,33 afin de produire un `double` valeur en tant que sortie. L’exemple accepte ensuite les valeurs transformées de la même `transformer` de l’objet et les imprime sur la console.  
  
 [!code-cpp[concrt-transformer-structure#1](../../parallel/concrt/codesnippet/CPP/asynchronous-message-blocks_5.cpp)]  
  
 Cet exemple génère la sortie suivante :  
  
```Output  
10.8914.5218.15  
```  
  
 Pour un exemple complet qui montre comment utiliser le `transformer` de classe, consultez la page [Comment : utiliser la classe transformer dans un Pipeline de données](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md).  
  
 [[Haut](#top)]  
  
##  <a name="a-namechoicea-choice-class"></a><a name="choice"></a> Classe Choice  
 Le [classes concurrency::choice](../../parallel/concrt/reference/choice-class.md) classe sélectionne le premier message disponible dans un jeu de sources. La `choice` classe représente un mécanisme de flux de contrôle au lieu d’un mécanisme de flux de données (la rubrique [bibliothèque d’Agents asynchrones](../../parallel/concrt/asynchronous-agents-library.md) décrit les différences entre les flux de données et de flux de contrôle).  
  
 Lecture d’un objet choice s’apparente à appeler la fonction API Windows `WaitForMultipleObjects` lorsqu’il a la `bWaitAll` paramètre la valeur `FALSE`. Toutefois, la `choice` classe lie les données à l’événement lui-même plutôt qu’à un objet de synchronisation externe.  
  
 En général, vous utilisez la `choice` classe avec le [concurrency::receive](../Topic/receive%20Function.md) fonction pour piloter le flux de contrôle dans votre application. Utilisez la `choice` classe lorsque vous devez sélectionner parmi des tampons de messages qui ont des types différents. Utilisez le `single_assignment` lorsque vous devez sélectionner parmi des tampons de messages qui ont le même type de classe.  
  
 L’ordre dans lequel vous liez les sources à un `choice` objet est important car il peut déterminer quel message est sélectionné. Par exemple, prenons le cas où vous liez plusieurs tampons de messages qui contiennent déjà un message à un `choice` objet. Le `choice` objet sélectionne le message à partir de la première source auquel il est lié. Après avoir lié toutes les sources, les `choice` objet conserve l’ordre dans lequel chaque source reçoit un message.  
  
### <a name="example"></a>Exemple  
 L’exemple suivant montre la structure de base de l’utilisation avec la `choice` classe. Cet exemple utilise le [concurrency::make_choice](../Topic/make_choice%20Function.md) fonction permettant de créer un `choice` objet qui sélectionne les trois blocs de messages. L’exemple calcule plusieurs nombres de Fibonacci et stocke chaque résultat dans un bloc de message différent. L’exemple imprime ensuite à la console un message basé sur l’opération terminé.  
  
 [!code-cpp[concrt-choice-structure#1](../../parallel/concrt/codesnippet/CPP/asynchronous-message-blocks_6.cpp)]  
  
 Cet exemple génère la sortie suivante :  
  
```Output  
fib35 received its value first. Result = 9227465  
```  
  
 Étant donné que la tâche qui calcule le 35<sup>th</sup> n’est pas garanti que le nombre de Fibonacci termine d’abord, la sortie de cet exemple peut varier.  
  
 Cet exemple utilise le [concurrency::parallel_invoke](../Topic/parallel_invoke%20Function.md) algorithme pour calculer les nombres de Fibonacci en parallèle. Pour plus d’informations sur `parallel_invoke`, consultez la page [des algorithmes parallèles](../../parallel/concrt/parallel-algorithms.md).  
  
 Pour un exemple complet qui montre comment utiliser le `choice` de classe, consultez la page [Comment : sélectionnez parmi les tâches terminées](../../parallel/concrt/how-to-select-among-completed-tasks.md).  
  
 [[Haut](#top)]  
  
##  <a name="a-namejoina-join-and-multitypejoin-classes"></a><a name="join"></a> Classes de jointure et multitype_join  
 Le [concurrency::join](../../parallel/concrt/reference/join-class.md) et [concurrency::multitype_join](../../parallel/concrt/reference/multitype-join-class.md) classes vous permettent d’attendre que chaque membre d’un ensemble de sources de recevoir un message. La `join` classe agit sur les objets sources qui ont un type de message commun. La `multitype_join` classe agit sur les objets sources qui peuvent avoir différents types de message.  
  
 Lecture à partir d’un `join` ou `multitype_join` objet s’apparente à l’appel de la fonction API Windows `WaitForMultipleObjects` lorsqu’il a la `bWaitAll` paramètre la valeur `TRUE`. Cependant, comme un `choice` objet, `join` et `multitype_join` objets utilisent un mécanisme d’événement qui lie les données à l’événement lui-même plutôt qu’à un objet de synchronisation externe.  
  
 Lecture à partir d’un `join` objet génère un std ::[vecteur](vector%20Class.md) objet. Lecture à partir d’un `multitype_join` objet génère un std ::[tuple](../../standard-library/tuple-class.md) objet. Les éléments apparaissent dans ces objets dans le même ordre que leurs mémoires tampons sources correspondantes sont liées à la `join` ou `multitype_join` objet. Étant donné que l’ordre dans lequel vous liez source met en mémoire tampon pour un `join` ou `multitype_join` est associé à l’ordre des éléments dans résultant `vector` ou `tuple` de l’objet, nous recommandons que vous ne pas dissocier une mémoire tampon source à partir d’une jointure. Cela peut entraîner un comportement non spécifié.  
  
### <a name="greedy-versus-non-greedy-joins"></a>Comportements gourmand et jointures Non gourmandes  
 Le `join` et `multitype_join` classes prennent en charge le concept de jointures non gourmandes et. Un *jointure gourmande* accepte un message de chacune de ses sources que les messages deviennent disponibles jusqu'à ce que tous les messages soient disponibles. Un *jointure non gourmande* reçoit les messages en deux phases. Tout d’abord, une jointure non gourmande attend jusqu'à ce qu’il reçoit un message de chacune de ses sources. Ensuite, une fois que tous les messages sources sont disponibles, une jointure non gourmande tente de réserver chacun de ces messages. Si chaque message peut être réservé, elle consomme tous les messages et les propage à sa cible. Dans le cas contraire, elle libère, ou annule, les réservations de messages et attend à nouveau que chaque source de recevoir un message.  
  
 Jointures gourmandes fonctionnent mieux que les jointures non gourmandes car elles acceptent les messages immédiatement. Toutefois, dans de rares cas, les jointures gourmandes peuvent provoquer des interblocages. Utilisez une jointure non gourmande lorsque vous avez plusieurs jointures qui contiennent un ou plusieurs objets sources partagés.  
  
### <a name="example"></a>Exemple  
 L’exemple suivant montre la structure de base de l’utilisation avec la `join` classe. Cet exemple utilise le [concurrency::make_join](../Topic/make_join%20Function.md) fonction permettant de créer un `join` objet qui reçoit de trois `single_assignment` objets. Cet exemple calcule plusieurs nombres de Fibonacci et stocke chaque résultat dans une autre `single_assignment` objet, puis imprime sur la console empêche que le `join` contient l’objet. Cet exemple est similaire à l’exemple de la `choice` classe, à ceci près que la `join` classe attend que tous les blocs de message source recevoir un message.  
  
 [!code-cpp[concrt-join-structure#1](../../parallel/concrt/codesnippet/CPP/asynchronous-message-blocks_7.cpp)]  
  
 Cet exemple génère la sortie suivante :  
  
```Output  
fib35 = 9227465fib37 = 24157817half_of_fib42 = 1.33957e+008  
```  
  
 Cet exemple utilise le [concurrency::parallel_invoke](../Topic/parallel_invoke%20Function.md) algorithme pour calculer les nombres de Fibonacci en parallèle. Pour plus d’informations sur `parallel_invoke`, consultez la page [des algorithmes parallèles](../../parallel/concrt/parallel-algorithms.md).  
  
 Pour obtenir des exemples complets qui montrent comment utiliser le `join` de classe, consultez la page [Comment : sélectionnez parmi les tâches terminées](../../parallel/concrt/how-to-select-among-completed-tasks.md) et [procédure pas à pas : à l’aide de la classe join pour empêcher l’interblocage](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md).  
  
 [[Haut](#top)]  
  
##  <a name="a-nametimera-timer-class"></a><a name="timer"></a> Classe Timer  
 L’accès concurrentiel ::[classe timer](../../parallel/concrt/reference/timer-class.md) agit comme une source de message. Un `timer` objet envoie un message à une cible après une période de temps s’est écoulé. La `timer` classe est utile lorsque vous devez différer l’envoi d’un message ou que vous souhaitez envoyer un message à intervalles réguliers.  
  
 La `timer` classe envoie son message pour qu’une seule cible. Si vous définissez la `_PTarget` paramètre dans le constructeur `NULL`, vous pouvez spécifier ultérieurement la cible en appelant le [Concurrency::ISource :: link_target](../Topic/source_block::link_target%20Method.md) méthode.  
  
 Un `timer` objet peut répétitif ou non répétitif. Pour créer une minuterie répétitive, passez `true` pour la `_Repeating` paramètre lorsque vous appelez le constructeur. Sinon, passez `false` pour la `_Repeating` paramètre pour créer une minuterie non répétitive. Si la minuterie est extensible, il envoie le même message à sa cible après chaque intervalle.  
  
 La bibliothèque d’Agents crée `timer` objets dans l’état non démarré. Pour démarrer un objet timer, appelez le [Concurrency::Timer :: Start](../Topic/timer::start%20Method.md) (méthode). Pour arrêter un `timer` d’objet, détruire l’objet ou l’appel de la [concurrency::timer::stop](../Topic/timer::stop%20Method.md) (méthode). Pour suspendre une minuterie répétitive, appelez le [concurrency::timer::pause](../Topic/timer::pause%20Method.md) (méthode).  
  
### <a name="example"></a>Exemple  
 L’exemple suivant montre la structure de base de l’utilisation avec la `timer` classe. L’exemple utilise `timer` et `call` objets pour signaler la progression d’une opération longue.  
  
 [!code-cpp[concrt-timer-structure#1](../../parallel/concrt/codesnippet/CPP/asynchronous-message-blocks_8.cpp)]  
  
 Cet exemple génère la sortie suivante :  
  
```Output  
Computing fib(42)..................................................result is 267914296  
```  
  
 Pour un exemple complet qui montre comment utiliser le `timer` de classe, consultez la page [Comment : envoyer un Message à intervalles réguliers](../../parallel/concrt/how-to-send-a-message-at-a-regular-interval.md).  
  
 [[Haut](#top)]  
  
##  <a name="a-namefilteringa-message-filtering"></a><a name="filtering"></a> Filtrage des messages  
 Lorsque vous créez un objet de bloc de message, vous pouvez fournir un *fonction filter* qui détermine si le bloc de message accepte ou rejette un message. Une fonction de filtre est un moyen utile pour garantir qu’un bloc de message reçoit uniquement certaines valeurs.  
  
 L’exemple suivant montre comment créer un `unbounded_buffer` objet qui utilise une fonction de filtre pour accepter uniquement les nombres pairs. Le `unbounded_buffer` objet rejette les nombres impairs et par conséquent ne propage pas les nombres impairs jusqu'à ses blocs cibles.  
  
 [!code-cpp[concrt-filter-function#1](../../parallel/concrt/codesnippet/CPP/asynchronous-message-blocks_9.cpp)]  
  
 Cet exemple génère la sortie suivante :  
  
```Output  
0 2 4 6 8  
```  
  
 Une fonction de filtre peut être une fonction lambda, un pointeur de fonction ou un objet de fonction. Chaque fonction de filtre prend l’une des formes suivantes.  
  
```Output  
bool (T)  
bool (T const &)  
```  
  
 Pour éviter la copie inutile des données, utilisez la deuxième forme lorsque vous avez un type d’agrégat est propagé par valeur.  
  
 Prend en charge le filtrage de message le *flux de données* modèle de programmation, dans lequel les composants exécutent des calculs lorsqu’ils reçoivent des données. Pour obtenir des exemples qui utilisent des fonctions de filtre pour contrôler le flux de données dans un réseau de passage de message, consultez [Comment : utiliser un filtre de bloc de Message](../../parallel/concrt/how-to-use-a-message-block-filter.md), [procédure pas à pas : création d’un Agent de flux de données](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md), et [procédure pas à pas : création d’un réseau de traitement d’Image](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md).  
  
 [[Haut](#top)]  
  
##  <a name="a-namereservationa-message-reservation"></a><a name="reservation"></a> Réservation de messages  
 *Réservation de message* permet à un bloc de message de réserver un message pour une utilisation ultérieure. En règle générale, la réservation de messages n’est pas utilisée directement. Cependant, message de présentation réservation peut vous aider à mieux comprendre le comportement de certains types de bloc de message prédéfinis.  
  
 Envisagez de jointures gourmandes et non gourmandes. Tous deux utilisent la réservation de messages pour réserver des messages pour une utilisation ultérieure. Un décrit précédemment, une jointure non gourmande reçoit les messages en deux phases. Pendant la première phase, non gourmand `join` objet attend que chacune de ses sources de recevoir un message. Une jointure non gourmande tente alors de réserver chacun de ces messages. Si chaque message peut être réservé, elle consomme tous les messages et les propage à sa cible. Dans le cas contraire, elle libère, ou annule, les réservations de messages et attend à nouveau que chaque source de recevoir un message.  
  
 Une jointure gourmande, qui lit également les messages d’entrée à partir de plusieurs sources, utilise la réservation de messages pour lire les messages supplémentaires en attendant de recevoir un message de chaque source. Par exemple, considérons une jointure gourmande qui reçoit des messages à partir de blocs de messages `A` et `B`. Si la jointure gourmande reçoit deux messages de B, mais n’a pas encore reçu un message de `A`, la jointure gourmande enregistre l’identificateur unique du message pour le deuxième message de `B`. Une fois la jointure gourmande reçoit un message à partir de `A` et propage ces messages, elle utilise l’identificateur de message enregistré afin de déterminer si le deuxième message de `B` est toujours disponible.  
  
 Vous pouvez utiliser la réservation de messages lorsque vous implémentez vos propres types de bloc de message personnalisé. Pour obtenir un exemple expliquant comment créer un type de bloc de message personnalisé, consultez la page [procédure pas à pas : création d’un bloc de Message personnalisé](../../parallel/concrt/walkthrough-creating-a-custom-message-block.md).  
  
 [[Haut](#top)]  
  
## <a name="see-also"></a>Voir aussi  
 [Bibliothèque d’Agents asynchrones](../../parallel/concrt/asynchronous-agents-library.md)


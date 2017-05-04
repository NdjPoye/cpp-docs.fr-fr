---
title: "Exceptions (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "01/22/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6cbdc1f1-e4d7-4707-a670-86365146432f
caps.latest.revision: 22
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 22
---
# Exceptions (C++/CX)
Dans [!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)] \([!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]\), la gestion des erreurs est basée sur les exceptions. Au niveau le plus fondamental, les composants [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] signalent les erreurs sous forme de valeurs HRESULT. Dans [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)], ces valeurs sont converties en exceptions fortement typées qui contiennent une valeur HRESULT et, dans [!INCLUDE[win81](../cppcx/includes/win81-md.md)], une description de chaîne accessible par programmation.  Les exceptions sont implémentées sous forme de `ref class` qui dérive de `Platform::Exception`.  L'espace de noms `Platform` définit des classes d'exception distinctes pour les valeurs HRESULT les plus courantes. Toutes les autres valeurs sont indiquées via la classe `Platform::COMException`. Toutes les classes d'exceptions ont un champ de [propriété Exception::HResult](../cppcx/exception-hresult-property.md) qui peut être utilisé pour récupérer le HRESULT d'origine. Dans [!INCLUDE[win81](../cppcx/includes/win81-md.md)], vous pouvez aussi consulter les informations de pile des appels du code utilisateur dans le débogueur, et vous en servir pour identifier la source d'origine de l'exception, même si celle\-ci provient du code écrit dans un autre langage que C\+\+.  
  
## Exceptions  
 Dans votre programme C\+\+, vous pouvez lever ou intercepter une exception qui provient d'une opération [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] et qui est dérivée de `std::exception` ou d'un type défini par l'utilisateur. Vous devez lever une exception [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] uniquement lorsqu'elle traversera la limite ABI \(Application Binary Interface\), par exemple lorsque le code qui intercepte votre exception est écrit en JavaScript. Lorsqu'une exception C\+\+ non [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] atteint la limite ABI, elle est convertie en exception `Platform::FailureException`, qui représente un HRESULT E\_FAIL. Pour plus d'informations sur l'ABI, consultez [Création de composants Windows Runtime en C\+\+](http://msdn.microsoft.com/library/5b7251e6-4271-4f13-af80-c1cf5b1489bf).  
  
 Vous pouvez déclarer [Platform::Exception](../cppcx/platform-exception-class.md) à l'aide de l'un des deux constructeurs qui acceptent soit un paramètre HRESULT, soit un paramètre HRESULT et un paramètre [Platform::String](../cppcx/platform-string-class.md)^ pouvant être passé via ABI à une application Windows Store qui le prend en charge. Vous pouvez aussi déclarer une exception à l'aide de l'une des deux surcharges de méthode [Exception::CreateException](../cppcx/exception-createexception-method.md) qui acceptent un paramètre HRESULT ou un paramètre HRESULT et un paramètre `Platform::String^`.  
  
## Exceptions standard  
 [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] prend en charge un ensemble d'exceptions standard qui représentent des erreurs HRESULT courantes. Chaque exception standard dérive de [Platform::COMException](../cppcx/platform-comexception-class.md), qui dérive à son tour de `Platform::Exception`. Lorsque vous levez une exception à travers la limite ABI, vous devez lever l'une des exceptions standard.  
  
 Vous ne pouvez pas dériver votre propre type d'exception de `Platform::Exception`. Pour lever une exception personnalisée, utilisez un HRESULT défini par l'utilisateur pour construire un objet `COMException`.  
  
 Le tableau ci\-dessous répertorie les exceptions standard.  
  
|Nom|HRESULT sous\-jacent|Description|  
|---------|--------------------------|-----------------|  
|COMException|*hresult défini par l’utilisateur*|Levée lorsqu'un HRESULT non reconnu est retourné d'un appel de méthode COM.|  
|AccessDeniedException|E\_ACCESSDENIED|Levée lorsque l'accès est refusé à une ressource ou à une fonctionnalité.|  
|ChangedStateException|E\_CHANGED\_STATE|Levée lorsque les méthodes d'un itérateur de collection ou d'une vue de collection sont appelées après la modification d'une collection parente, invalidant ainsi les résultats de la méthode.|  
|ClassNotRegisteredException|REGDB\_E\_CLASSNOTREG|Levée lorsqu'une classe COM n'a pas été inscrite.|  
|DisconnectedException|RPC\_E\_DISCONNECTED|Levée lorsqu'un objet est déconnecté de ses clients.|  
|FailureException|E\_FAIL|Levée lorsqu'une opération échoue.|  
|InvalidArgumentException|E\_INVALIDARG|Levée lorsque l'un des arguments fournis à une méthode n'est pas valide.|  
|InvalidCastException|E\_NOINTERFACE|Levée lorsqu'un type ne peut pas être casté en un autre type.|  
|NotImplementedException|E\_NOTIMPL|Levée si une méthode d'interface n'a pas été implémentée pour une classe.|  
|NullReferenceException|E\_POINTER|Levée lors d'une tentative de suppression de la référence à une référence d'objet null.|  
|ObjectDisposedException|RO\_E\_CLOSED|Levée lorsqu'une opération est exécutée sur un objet supprimé.|  
|OperationCanceledException|E\_ABORT|Levée lorsqu'une opération est abandonnée.|  
|OutOfBoundsException|E\_BOUNDS|Levée lorsqu'une opération tente d'accéder aux données en dehors de la plage valide.|  
|OutOfMemoryException|E\_OUTOFMEMORY|Levée en cas de mémoire insuffisante pour terminer l'opération.|  
|WrongThreadException|RPC\_E\_WRONG\_THREAD|Levée lorsqu'un thread effectue un appel via un pointeur d'interface qui concerne un objet proxy qui n'appartient pas à l'apartment du thread.|  
  
## Propriétés HRESULT et Message  
 Toutes les exceptions ont une propriété [HRESULT](../cppcx/comexception-hresult-property.md) et une propriété [Message](../cppcx/comexception-message-property.md). La propriété [Exception::HResult](../cppcx/exception-hresult-property.md) obtient la valeur HRESULT numérique sous\-jacente de l'exception. La propriété [Exception::Message](../cppcx/exception-message-property.md) obtient la chaîne fournie par le système qui décrit l'exception. Dans [!INCLUDE[win8](../cppcx/includes/win8-md.md)], le message est disponible uniquement dans le débogueur et est en lecture seule. Cela signifie que vous ne pouvez pas le modifier quand vous levez de nouveau l'exception. Dans [!INCLUDE[win81](../cppcx/includes/win81-md.md)], vous pouvez accéder à la chaîne de message par programmation et fournir un nouveau message si vous levez de nouveau l'exception. Des informations plus riches relatives aux piles des appels sont également disponibles dans le débogueur, notamment les piles des appels correspondant aux appels de méthode asynchrones.  
  
## Exemples  
 L'exemple ci\-dessous montre comment lever une exception [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] pour les opérations synchrones :  
  
 [!code-cpp[cx_exceptions#01](../snippets/cpp/VS_Snippets_Misc/cx_exceptions/cpp/class1.cpp#01)]  
  
 L'exemple ci\-dessous montre comment intercepter l'exception.  
  
 [!code-cpp[cx_exceptions#02](../snippets/cpp/VS_Snippets_Misc/cx_exceptions/cpp/class1.cpp#02)]  
  
 Pour intercepter les exceptions levées pendant une opération asynchrone, utilisez la classe de tâche et ajoutez une continuation de gestion des erreurs. La continuation de gestion des erreurs marshale les exceptions levées sur d'autres threads vers le thread appelant afin de gérer toutes les exceptions éventuelles en un seul point de votre code. Pour plus d’informations sur la programmation asynchrone, consultez [Programmation asynchrone en C\+\+](http://msdn.microsoft.com/library/windows/apps/Hh780559.aspx).  
  
## Événement UnhandledErrorDetected  
 Dans [!INCLUDE[win81](../cppcx/includes/win81-md.md)], vous pouvez vous abonner à l’événement statique [Windows::ApplicationModel::Core::CoreApplication::UnhandledErrorDetected](http://msdn.microsoft.com/library/windows/apps/windows.applicationmodel.core.coreapplication.unhandlederrordetected.aspx), qui permet d’accéder aux erreurs non gérées qui sont sur le point d’interrompre le processus. Indépendamment de l’origine de l’erreur, il atteint ce gestionnaire en tant qu’objet [Windows::ApplicationModel::Core::UnhandledError](http://msdnstage.redmond.corp.microsoft.com/library/windows/apps/windows.applicationmodel.core.unhandlederror.aspx) passé avec les arguments d’événement. Lorsque vous appelez `Propagate` sur l'objet, il crée et lève une exception `Platform::*Exception` dont le type correspond au code d'erreur. Dans les blocs catch, vous pouvez enregistrer l'état utilisateur, le cas échéant. Vous pouvez ensuite permettre au processus de se terminer en appelant `throw`, ou vous pouvez faire en sorte de restaurer le programme à un état connu. L'exemple suivant illustre le modèle de base :  
  
```  
  
// In app.xaml.h:  
void OnUnhandledException(Platform::Object^ sender, Windows::ApplicationModel::Core::UnhandledErrorDetectedEventArgs^ e);  
  
// In app.xaml.cpp  
  
// Subscribe to the event, for example in the app class constructor:  
Windows::ApplicationModel::Core::CoreApplication::UnhandledErrorDetected += ref new EventHandler<UnhandledErrorDetectedEventArgs^>(this, &App::OnUnhandledException);  
  
// Event handler implementation:  
void App::OnUnhandledException(Platform::Object^ sender, Windows::ApplicationModel::Core::UnhandledErrorDetectedEventArgs^ e)  
{  
    auto err = e->UnhandledError;  
  
    if (!err->Handled) //Propagate has not been called on it yet.  
{  
     try  
    {  
        err->Propagate();  
    }  
    // Catch any specific exception types if you know how to handle them  
    catch (AccessDeniedException^ ex)  
    {  
        // TODO: Log error and either take action to recover  
        // or else re-throw exception to continue fail-fast  
    }  
  
}  
  
```  
  
## Notes  
 [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] n'utilise pas la clause `finally`.  
  
## Voir aussi  
 [Référence du langage Visual C\+\+](../cppcx/visual-c-language-reference-c-cx.md)   
 [Référence aux espaces de noms](../cppcx/namespaces-reference-c-cx.md)
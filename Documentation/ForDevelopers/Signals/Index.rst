﻿.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../Includes.txt


.. _signals:

Signal slots
============

Signals
-------
Signals are currently only used in the actions of the payment controller to control the behavior of the output
and the processing of the payment of a registration.

.. t3-field-list-table::
 :header-rows: 1

 - :Class:
         Class:

   :Name:
         Name:

   :Arguments:
         Arguments:

   :Description:
         Description:

 - :Class:
         DERHANSEN\SfEventMgt\Controller\Event

   :Name:
         listActionBeforeRenderView

   :Arguments:
         &$values, $this

   :Description:
         Signal is called before rendering the list view. An array with all view values is passed by reference.

 - :Class:
         DERHANSEN\SfEventMgt\Controller\Event

   :Name:
         calendarActionBeforeRenderView

   :Arguments:
         &$values, $this

   :Description:
         Signal is called before rendering the calendar view. An array with all view values is passed by reference.

 - :Class:
         DERHANSEN\SfEventMgt\Controller\Event

   :Name:
         detailActionBeforeRenderView

   :Arguments:
         &$values, $this

   :Description:
         Signal is called before rendering the detail view. An array with all view values is passed by reference.

 - :Class:
         DERHANSEN\SfEventMgt\Controller\Event

   :Name:
         registrationActionBeforeRenderView

   :Arguments:
         &$values, $this

   :Description:
         Signal is called before rendering the registration view. An array with all view values is passed by reference.

 - :Class:
         DERHANSEN\SfEventMgt\Controller\Event

   :Name:
         saveRegistrationActionAfterRegistrationSaved

   :Arguments:
         $registration, $this

   :Description:
         Signal is called after a registration is saved. The registration is passed to the signal.

 - :Class:
         DERHANSEN\SfEventMgt\Controller\Event

   :Name:
         confirmRegistrationActionBeforeRenderView

   :Arguments:
         &$values, $this

   :Description:
         Signal is called before rendering the confirmRegistration view. An array with all view values is passed by reference.

 - :Class:
         DERHANSEN\SfEventMgt\Controller\Event

   :Name:
         cancelRegistrationActionWaitlistMoveUp

   :Arguments:
         $event, $this

   :Description:
         Signal is after a registration is cancelled. Use this signal to move registrations from the waitlist up to
         the confirmed registrations.

 - :Class:
         DERHANSEN\SfEventMgt\Controller\Event

   :Name:
         cancelRegistrationActionBeforeRenderView

   :Arguments:
         &$values, $this

   :Description:
         Signal is called before rendering the cancelRegistration view. An array with all view values is passed by reference.

 - :Class:
         DERHANSEN\SfEventMgt\Controller\Event

   :Name:
         searchActionBeforeRenderView

   :Arguments:
         &$values, $this

   :Description:
         Signal is called before rendering the search view. An array with all view values is passed by reference.

 - :Class:
         DERHANSEN\SfEventMgt\Controller\Payment

   :Name:
         'redirectActionBeforeRedirect' + ucfirst($paymentMethod)

   :Arguments:
         &$values, &$updateRegistration, $registration, $this

   :Description:
         Signal is called before rendering the redirect view. Use this signal to create the views HTML content,
         that redirects the user to the payment providers payment page.

 - :Class:
         DERHANSEN\SfEventMgt\Controller\Payment

   :Name:
         'successActionProcessSuccess' + ucfirst($paymentMethod)

   :Arguments:
         &$values, &$updateRegistration, $registration, GeneralUtility::_GET(), $this

   :Description:
         Signal is called before rendering the success view. Use this signal to create the views HTML content
         and also use this signal to modify the payment status of the registration after a successful payment.

 - :Class:
         DERHANSEN\SfEventMgt\Controller\Payment

   :Name:
         'failureActionProcessFailure' + ucfirst($paymentMethod)

   :Arguments:
         &$values, &$updateRegistration, &$removeRegistration, $registration, GeneralUtility::_GET(), $this

   :Description:
         Signal is called before rendering the failure view. Use this signal to create the views HTML content
         and also use this signal to modify/delete the registration after a failed payment.

 - :Class:
         DERHANSEN\SfEventMgt\Controller\Payment

   :Name:
         'cancelActionProcessCancel' + ucfirst($paymentMethod)

   :Arguments:
         &$values, &$updateRegistration, &$removeRegistration, $registration, GeneralUtility::_GET(), $this

   :Description:
         Signal is called before rendering the cancel view. Use this signal to create the views HTML content
         and also use this signal to modify/delete the registration after a cancelled payment.

 - :Class:
         DERHANSEN\SfEventMgt\Controller\Payment

   :Name:
         'notifyActionProcessNotify' + ucfirst($paymentMethod)

   :Arguments:
         &$values, &$updateRegistration, $registration, GeneralUtility::_GET(), $this

   :Description:
         Signal is called before rendering the notify view. Use this signal to create the views HTML content
         and also use this signal to modify the registration when the payment provider supports a server to server
         nofitication URL.

 - :Class:
         DERHANSEN\SfEventMgt\Domain\Model\Repository\EventRepository

   :Name:
         findDemandedModifyQueryConstraints

   :Arguments:
         &$constraints, $query, $eventDemand, $this

   :Description:
         Signal is called after all query constraints are collected. The signal enables the possibility to add/modify
         the query constraints for the findDemanded function. Very usefull, when you extend the eventDemand with custom
         properties.



.. _logging_status:

All processes should publish their log messages with process status to Process Manager. These processes include applications, simulations, services, and test runs.

Topic:
^^^^^^^

Log message with process status should be published on the following topic. Process id should be attached to the topic name at the end.
	
.. code-block:: console

	goss.gridappsd.simulation.log.[simulation_id]
	goss.gridappsd.service.log.[service_id]
	goss.gridappsd.application.log.[app_id]
	goss.gridappsd.test.log.[test_id]
	
Message structure:
^^^^^^^^^^^^^^^^^^

.. code-block:: console

	{
		"source": "",
		"processId": "",
		"timestamp": "",
		"processStatus": "[STARTED|STOPPED|RUNNING|ERROR|PASSED|FAILED]",
		"logMessage": "",
		"logLevel": "[INFO|DEBUG|ERROR]",
		"storeToDb": [true|false]
	}
	
Receiving multiple logs:
^^^^^^^^^^^^^^^^^^^^^^^

User can either subscribe to individual process's log by subscribing to topics mentioned above or receive all logs of a type by subscribing to following topics.

.. code-block:: console

	goss.gridappsd.simulation.log.*
	goss.gridappsd.service.log.*
	goss.gridappsd.application.log.*
	goss.gridappsd.test.log.*

Similarly, to receive to all logs subscribe to following topic:

.. code-block:: console

	goss.gridappsd.*.log.*

 

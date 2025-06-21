.. _chapter-interface:

=========
Interface
=========


.. _section-interface-iottopics:

IoT Topics
==========

.. list-table::
    :header-rows: 1
    :widths: 1, 1, 3

    * - Topic
      - Pub/Sub
      - Description
    * - aws/questar/soshinki/noise/data_chunk
      - Publish
      - :ref:`最小計測単位 <section-measureparameters-noise>` の収集騒音計測データの送信先
        
        Destination of collected noise data in the :ref:`minimum measurement unit <section-measureparameters-noise>`
    * - aws/questar/soshinki/noise/data_sum
      - Publish
      - :ref:`最小集計単位 <section-measureparameters-noise>` の集計騒音計測データの送信先
        
        Destination of noise measurement data in the :ref:`minimum aggregate unit <section-measureparameters-noise>`
    * - aws/questar/soshinki/vibration/data_chunk
      - Publish
      - :ref:`最小計測単位 <section-measureparameters-vibration>` の収集振動計測データの送信先
        
        Destination of collected vibration data in the :ref:`minimum measurement unit <section-measureparameters-vibration>`
    * - aws/questar/soshinki/vibration/data_sum
      - Publish
      - :ref:`最小集計単位 <section-measureparameters-vibration>` の集計振動計測データの送信先
        
        Destination of vibration measurement data in the :ref:`minimum aggregate unit <section-measureparameters-vibration>`
    * - aws/questar/soshinki/weather/data_chunk
      - Publish
      - :ref:`最小計測単位 <section-measureparameters-weather>` の収集気象計測データの送信先
        
        Destination of collected weather data in the :ref:`minimum measurement unit <section-measureparameters-weather>`
    * - aws/questar/soshinki/weather/data_sum
      - Publish
      - :ref:`最小集計単位 <section-measureparameters-weather>` の集計気象計測データの送信先
        
        Destination of weather measurement data in the :ref:`minimum aggregate unit <section-measureparameters-weather>`

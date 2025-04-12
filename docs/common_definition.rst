.. _chapter-commondefinition:

=================
Common Definition
=================

.. _section-commondefinition-devicetype:

Device Type
===========

.. list-table::
    :header-rows: 1
    :widths: 1, 2

    * - Type String
      - Vendor/Model
    * - noise1
      - リオン [RION] NL-42A
    * - noise2
      - リオン [RION] NL-43
    * - vibration1
      - リオン [RION] VM-55
    * - vibration2
      - 予約 (リオン [RION] VM-55以外の振動計)
        
        Reserved (for other vibration than RION VM-55 )
    * - noise4
      - アコー [ACO] TYPE3666 内蔵騒音計
        
        Noise measure embedded in unit
    * - vibration4
      - アコー [ACO] TYPE3666 内蔵振動計
        
        Vibration measure embedded in unit
    * - weather1
      - misol Weather Station WH24C

.. _section-commondefinition-datatype:

Data Type
=========

.. list-table::
    :header-rows: 1
    :widths: 1, 2

    * - Type String
      - Description
    * - chunk
      - 最小計測単位時間の収集データ
        
        Collected data in minimum measurement unit time
    * - sum
      - 最小集計単位時間の計測データ
        
        Measurement data in minimum aggregation unit time

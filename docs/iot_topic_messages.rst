.. _chapter-iottopicmessages:

==================
IoT Topic Messages
==================


.. _section-iottopicmessages-datachunk:

noise1/data_chunk
=================

*Target Measures*
^^^^^^^^^^^^^^^^^

- リオン [RION] NL-42A

*Destination IoT Topic*
^^^^^^^^^^^^^^^^^^^^^^^

aws/questar/soshinki/noise/data_chunk

*Example*
^^^^^^^^^

.. code-block:: json

    {
      "device_id": "SK000010",
      "device_data_type": "noise1/chunk",
      "data_version": "20250402",
      "data_no": 1,
      "data_key": "dod",
      "data_aux": "RION NL-42A",
      "data_chunk": [
        {
          "timestamp": 1744262056460,
          "Lp": 67.0,
          "Lmax": 73.6,
          "Lmin": 65.5,
          "L5": 73.4,
          "L10": 73.4,
          "L50": 70.0,
          "L90": 69.3,
          "L95": 66.3
        },
        {
          "timestamp": 1744262057462,
          "Lp": 70.8,
          "Lmax": 73.6,
          "Lmin": 59.4,
          "L5": 73.4,
          "L10": 72.6,
          "L50": 69.5,
          "L90": 61.4,
          "L95": 60.6
        },
        {
          "timestamp": 1744262058463,
          "Lp": 69.7,
          "Lmax": 73.6,
          "Lmin": 59.4,
          "L5": 72.8,
          "L10": 72.6,
          "L50": 70.0,
          "L90": 62.8,
          "L95": 60.6
        },
        {
          "timestamp": 1744262059464,
          "Lp": 70.8,
          "Lmax": 73.6,
          "Lmin": 53.3,
          "L5": 72.8,
          "L10": 72.6,
          "L50": 69.4,
          "L90": 60.0,
          "L95": 58.1
        },
        {
          "timestamp": 1744262060466,
          "Lp": 68.6,
          "Lmax": 74.4,
          "Lmin": 53.3,
          "L5": 73.4,
          "L10": 73.1,
          "L50": 69.6,
          "L90": 60.6,
          "L95": 58.1
        },
        {
          "timestamp": 1744262061467,
          "Lp": 73.8,
          "Lmax": 77.4,
          "Lmin": 53.3,
          "L5": 75.2,
          "L10": 73.4,
          "L50": 70.1,
          "L90": 60.6,
          "L95": 59.8
        },
        {
          "timestamp": 1744262062468,
          "Lp": 66.2,
          "Lmax": 77.4,
          "Lmin": 53.3,
          "L5": 74.0,
          "L10": 73.8,
          "L50": 70.8,
          "L90": 61.4,
          "L95": 59.8
        },
        {
          "timestamp": 1744262063471,
          "Lp": 68.0,
          "Lmax": 77.4,
          "Lmin": 53.3,
          "L5": 74.0,
          "L10": 73.6,
          "L50": 70.1,
          "L90": 62.2,
          "L95": 60.0
        },
        {
          "timestamp": 1744262064471,
          "Lp": 69.5,
          "Lmax": 77.4,
          "Lmin": 53.3,
          "L5": 73.9,
          "L10": 73.4,
          "L50": 69.6,
          "L90": 62.2,
          "L95": 60.0
        },
        {
          "timestamp": 1744262065473,
          "Lp": 66.2,
          "Lmax": 77.4,
          "Lmin": 53.3,
          "L5": 73.9,
          "L10": 73.4,
          "L50": 69.5,
          "L90": 62.0,
          "L95": 60.0
        }
      ]
    }

*Field Items*
^^^^^^^^^^^^^

.. list-table::
    :header-rows: 1
    :widths: 1, 1, 3

    * - Name
      - Type
      - Description
    * - device_id
      - string
      - 端末固有のID
        
        Unique ID of the terminal which sent this data
    * - device_data_type
      - string
      - :ref:`noise1 <section-commondefinition-devicetype>`/:ref:`chunk <section-commondefinition-datatype>`
    * - data_version
      - string
      - データ形式のバージョン　データ形式が部分的に変更された場合に本値が更新される
        
        Version of data format. This value will be updated when the data format is partially changed.
    * - data_no
      - number
      - データの順序番号　端末起動後計測開始時に 1 から始まり、最小計測単位データの個数分増加していく
        
        Sequential number of data. Starts at 1 when measurement starts after the terminal startup, and increases by the number of minimum measurement unit data.
    * - data_key
      - string
      - 計測データ取得に使用された計器固有のコマンド
        
        Device-specific commands used to acquire this measurement data
    * - data_aux
      - string
      - データに関する補足情報　現在は計器のメーカーとモデル名が格納される
        
        Stores auxiliary information about this data, currently vendor and model names of the target measure.
    * - data_chunk
      - array<json-object>
      - :ref:`最小計測単位 <section-measures-noise>` の収集計測データが格納される配列
        
        Array stores the collected measurement data in the :ref:`minimum measurement unit <section-measures-noise>`.
    * - timestamp
      - number
      - 計測データの取得時刻　ミリ秒単位UNIX時刻 (UTC)
        
        Time at which this data entry was acquired. UNIX time in milliseconds (UTC)
    * - Lp
      - number
      - 計測データ取得時の騒音最新値
        
        Latest noise value at this data entry was acquired
    * - Lmax
      - number
      - 最小計測単位時間内での騒音最大値
        
        Maximum noise value within the minimum measurement unit time
    * - Lmin
      - number
      - 最小計測単位時間内での騒音最小値
        
        Minimum noise value within the minimum measurement unit time
    * - L5
      - number
      - 最小計測単位時間内での騒音L5値
        
        L5 noise value within the minimum measurement unit time
    * - L10
      - number
      - 最小計測単位時間内での騒音L10値
        
        L10 noise value within the minimum measurement unit time
    * - L50
      - number
      - 最小計測単位時間内での騒音L50値
        
        L50 noise value within the minimum measurement unit time
    * - L90
      - number
      - 最小計測単位時間内での騒音L90値
        
        L90 noise value within the minimum measurement unit time
    * - L95
      - number
      - 最小計測単位時間内での騒音L95値
        
        L95 noise value within the minimum measurement unit time

noise2/data_chunk
=================

*Target Measures*
^^^^^^^^^^^^^^^^^

- リオン [RION] NL-43

*Destination IoT Topic*
^^^^^^^^^^^^^^^^^^^^^^^

aws/questar/soshinki/noise/data_chunk

*Example*
^^^^^^^^^

.. code-block:: json

    {
      "device_id": "SK000010",
      "device_data_type": "noise2/chunk",
      "data_version": "20250402",
      "data_no": 1,
      "data_key": "dod",
      "data_aux": "RION NL-43",
      "data_chunk": [
        {
          "timestamp": 1744262292001,
          "Lp": 71.1,
          "Lmax": 76.6,
          "Lmin": 69.4,
          "L5": 76.4,
          "L10": 76.1,
          "L50": 73.3,
          "L90": 70.8,
          "L95": 70.8
        },
        {
          "timestamp": 1744262293005,
          "Lp": 68.5,
          "Lmax": 76.6,
          "Lmin": 65.3,
          "L5": 76.1,
          "L10": 76.0,
          "L50": 72.4,
          "L90": 68.5,
          "L95": 67.6
        },
        {
          "timestamp": 1744262294008,
          "Lp": 73.4,
          "Lmax": 76.6,
          "Lmin": 65.3,
          "L5": 76.1,
          "L10": 74.5,
          "L50": 72.4,
          "L90": 68.5,
          "L95": 68.0
        },
        {
          "timestamp": 1744262295008,
          "Lp": 58.2,
          "Lmax": 76.6,
          "Lmin": 58.2,
          "L5": 76.0,
          "L10": 74.5,
          "L50": 72.4,
          "L90": 68.0,
          "L95": 65.0
        },
        {
          "timestamp": 1744262296010,
          "Lp": 51.5,
          "Lmax": 76.6,
          "Lmin": 51.5,
          "L5": 76.0,
          "L10": 74.3,
          "L50": 71.2,
          "L90": 58.2,
          "L95": 57.5
        },
        {
          "timestamp": 1744262297012,
          "Lp": 57.9,
          "Lmax": 76.6,
          "Lmin": 47.0,
          "L5": 75.0,
          "L10": 74.0,
          "L50": 70.7,
          "L90": 56.3,
          "L95": 53.3
        },
        {
          "timestamp": 1744262298013,
          "Lp": 51.3,
          "Lmax": 76.6,
          "Lmin": 46.7,
          "L5": 75.0,
          "L10": 73.9,
          "L50": 68.9,
          "L90": 53.4,
          "L95": 51.3
        },
        {
          "timestamp": 1744262299014,
          "Lp": 70.8,
          "Lmax": 76.6,
          "Lmin": 46.7,
          "L5": 74.5,
          "L10": 73.9,
          "L50": 68.9,
          "L90": 54.1,
          "L95": 51.3
        },
        {
          "timestamp": 1744262300016,
          "Lp": 60.2,
          "Lmax": 76.6,
          "Lmin": 46.7,
          "L5": 74.5,
          "L10": 73.7,
          "L50": 68.4,
          "L90": 54.4,
          "L95": 51.5
        },
        {
          "timestamp": 1744262301017,
          "Lp": 63.9,
          "Lmax": 76.6,
          "Lmin": 42.4,
          "L5": 74.3,
          "L10": 73.6,
          "L50": 67.1,
          "L90": 51.3,
          "L95": 47.1
        }
      ]
    }

*Field Items*
^^^^^^^^^^^^^

.. list-table::
    :header-rows: 1
    :widths: 1, 1, 3

    * - Name
      - Type
      - Description
    * - device_id
      - string
      - 端末固有のID
        
        Unique ID of the terminal which sent this data
    * - device_data_type
      - string
      - :ref:`noise2 <section-commondefinition-devicetype>`/:ref:`chunk <section-commondefinition-datatype>`
    * - data_version
      - string
      - データ形式のバージョン　データ形式が部分的に変更された場合に本値が更新される
        
        Version of data format. This value will be updated when the data format is partially changed.
    * - data_no
      - number
      - データの順序番号　端末起動後計測開始時に 1 から始まり、最小計測単位データの個数分増加していく
        
        Sequential number of data. Starts at 1 when measurement starts after the terminal startup, and increases by the number of minimum measurement unit data.
    * - data_key
      - string
      - 計測データ取得に使用された計器固有のコマンド
        
        Device-specific commands used to acquire this measurement data
    * - data_aux
      - string
      - データに関する補足情報　現在は計器のメーカーとモデル名が格納される
        
        Stores auxiliary information about this data, currently vendor and model names of the target measure.
    * - data_chunk
      - array<json-object>
      - :ref:`最小計測単位 <section-measures-noise>` の収集計測データが格納される配列
        
        Array stores the collected measurement data in the :ref:`minimum measurement unit <section-measures-noise>`.
    * - timestamp
      - number
      - 計測データの取得時刻　ミリ秒単位UNIX時刻 (UTC)
        
        Time at which this data entry was acquired. UNIX time in milliseconds (UTC)
    * - Lp
      - number
      - 計測データ取得時の騒音最新値
        
        Latest noise value at this data entry was acquired
    * - Lmax
      - number
      - 最小計測単位時間内での騒音最大値
        
        Maximum noise value within the minimum measurement unit time
    * - Lmin
      - number
      - 最小計測単位時間内での騒音最小値
        
        Minimum noise value within the minimum measurement unit time
    * - L5
      - number
      - 最小計測単位時間内での騒音L5値
        
        L5 noise value within the minimum measurement unit time
    * - L10
      - number
      - 最小計測単位時間内での騒音L10値
        
        L10 noise value within the minimum measurement unit time
    * - L50
      - number
      - 最小計測単位時間内での騒音L50値
        
        L50 noise value within the minimum measurement unit time
    * - L90
      - number
      - 最小計測単位時間内での騒音L90値
        
        L90 noise value within the minimum measurement unit time
    * - L95
      - number
      - 最小計測単位時間内での騒音L95値
        
        L95 noise value within the minimum measurement unit time

noise4/data_chunk 
=================

*Target Measure*
^^^^^^^^^^^^^^^^

- | アコー [ACO] TYPE3666 内蔵騒音計
  | Noise measure embedded in unit

*Destination IoT Topic*
^^^^^^^^^^^^^^^^^^^^^^^

aws/questar/soshinki/noise/data_chunk

*Example*
^^^^^^^^^

.. code-block:: json

    {
      "device_id": "SK000010",
      "device_data_type": "noise4/chunk",
      "data_version": "20250402",
      "data_no": 1,
      "data_key": "as",
      "data_aux": "ACO TYPE3666",
      "data_chunk": [
        {
          "timestamp": 1744269795391,
          "Lp": 43.7
        },
        {
          "timestamp": 1744269796366,
          "Lp": 50.0
        },
        {
          "timestamp": 1744269797405,
          "Lp": 41.3
        },
        {
          "timestamp": 1744269798381,
          "Lp": 47.8
        },
        {
          "timestamp": 1744269799422,
          "Lp": 49.4
        },
        {
          "timestamp": 1744269800397,
          "Lp": 45.9
        },
        {
          "timestamp": 1744269801373,
          "Lp": 49.3
        },
        {
          "timestamp": 1744269802411,
          "Lp": 44.7
        },
        {
          "timestamp": 1744269803387,
          "Lp": 41.0
        },
        {
          "timestamp": 1744269804364,
          "Lp": 52.1
        },
        {
          "timestamp": 1744269805403,
          "Lp": 56.5
        },
        {
          "timestamp": 1744269806379,
          "Lp": 53.4
        }
      ]
    }

*Field Items*
^^^^^^^^^^^^^

.. list-table::
    :header-rows: 1
    :widths: 1, 1, 3

    * - Name
      - Type
      - Description
    * - device_id
      - string
      - 端末固有のID
        
        Unique ID of the terminal which sent this data
    * - device_data_type
      - string
      - :ref:`noise4 <section-commondefinition-devicetype>`/:ref:`chunk <section-commondefinition-datatype>`
    * - data_version
      - string
      - データ形式のバージョン　データ形式が部分的に変更された場合に本値が更新される
        
        Version of data format. This value will be updated when the data format is partially changed.
    * - data_no
      - number
      - データの順序番号　端末起動後計測開始時に 1 から始まり、最小計測単位データの個数分増加していく
        
        Sequential number of data. Starts at 1 when measurement starts after the terminal startup, and increases by the number of minimum measurement unit data.
    * - data_key
      - string
      - 計測データ取得に使用された計器固有のコマンド
        
        Device-specific commands used to acquire this measurement data
    * - data_aux
      - string
      - データに関する補足情報　現在は計器のメーカーとモデル名が格納される
        
        Stores auxiliary information about this data, currently vendor and model names of the target measure.
    * - data_chunk
      - array<json-object>
      - :ref:`最小計測単位 <section-measures-noise>` の収集計測データが格納される配列
        
        Array stores the collected measurement data in the :ref:`minimum measurement unit <section-measures-noise>`.
    * - timestamp
      - number
      - 計測データの取得時刻　ミリ秒単位UNIX時刻 (UTC)
        
        Time at which this data entry was acquired. UNIX time in milliseconds (UTC)
    * - Lp
      - number
      - 計測データ取得時の騒音最新値
        
        Latest noise value at this data entry was acquired

vibration1/data_chunk
=====================

*Target Measures*
^^^^^^^^^^^^^^^^^

- リオン [RION] VM-55

*Destination IoT Topic*
^^^^^^^^^^^^^^^^^^^^^^^

aws/questar/soshinki/vibration/data_chunk

*Example*
^^^^^^^^^

.. code-block:: json

    {
      "device_id": "SK000010",
      "device_data_type": "vibration1/chunk",
      "data_version": "20250402",
      "data_no": 1,
      "data_key": "dod",
      "data_aux": "RION VM-55",
      "data_chunk": [
        {
          "timestamp": 1744262454723,
          "Lv": 30.3,
          "Lvmax": 31.7,
          "Lvmin": 30.5,
          "L5": 31.4,
          "L10": 31.4,
          "L50": 31.1,
          "L90": 30.6,
          "L95": 30.5
        },
        {
          "timestamp": 1744262455725,
          "Lv": 31.3,
          "Lvmax": 32.2,
          "Lvmin": 29.8,
          "L5": 32.0,
          "L10": 32.0,
          "L50": 31.2,
          "L90": 30.3,
          "L95": 30.0
        },
        {
          "timestamp": 1744262456726,
          "Lv": 33.0,
          "Lvmax": 33.0,
          "Lvmin": 29.8,
          "L5": 32.8,
          "L10": 32.6,
          "L50": 31.3,
          "L90": 30.5,
          "L95": 30.0
        },
        {
          "timestamp": 1744262457728,
          "Lv": 32.7,
          "Lvmax": 33.9,
          "Lvmin": 29.8,
          "L5": 33.6,
          "L10": 33.2,
          "L50": 31.5,
          "L90": 30.5,
          "L95": 30.3
        },
        {
          "timestamp": 1744262458730,
          "Lv": 33.6,
          "Lvmax": 34.0,
          "Lvmin": 29.8,
          "L5": 33.8,
          "L10": 33.6,
          "L50": 31.9,
          "L90": 30.6,
          "L95": 30.3
        },
        {
          "timestamp": 1744262459731,
          "Lv": 32.2,
          "Lvmax": 34.0,
          "Lvmin": 29.8,
          "L5": 33.8,
          "L10": 33.6,
          "L50": 32.1,
          "L90": 30.7,
          "L95": 30.5
        },
        {
          "timestamp": 1744262460733,
          "Lv": 30.9,
          "Lvmax": 34.0,
          "Lvmin": 29.8,
          "L5": 33.7,
          "L10": 33.5,
          "L50": 32.0,
          "L90": 30.8,
          "L95": 30.5
        },
        {
          "timestamp": 1744262461734,
          "Lv": 31.2,
          "Lvmax": 34.0,
          "Lvmin": 29.8,
          "L5": 33.7,
          "L10": 33.4,
          "L50": 31.6,
          "L90": 30.4,
          "L95": 30.1
        },
        {
          "timestamp": 1744262462737,
          "Lv": 32.9,
          "Lvmax": 34.0,
          "Lvmin": 29.8,
          "L5": 33.6,
          "L10": 33.4,
          "L50": 31.5,
          "L90": 30.4,
          "L95": 30.1
        },
        {
          "timestamp": 1744262463739,
          "Lv": 31.9,
          "Lvmax": 34.0,
          "Lvmin": 29.8,
          "L5": 33.6,
          "L10": 33.4,
          "L50": 31.7,
          "L90": 30.5,
          "L95": 30.3
        }
      ]
    }

*Field Items*
^^^^^^^^^^^^^

.. list-table::
    :header-rows: 1
    :widths: 1, 1, 3

    * - Name
      - Type
      - Description
    * - device_id
      - string
      - 端末固有のID
        
        Unique ID of the terminal which sent this data
    * - device_data_type
      - string
      - :ref:`vibration1 <section-commondefinition-devicetype>`/:ref:`chunk <section-commondefinition-datatype>`
    * - data_version
      - string
      - データ形式のバージョン　データ形式が部分的に変更された場合に本値が更新される
        
        Version of data format. This value will be updated when the data format is partially changed.
    * - data_no
      - number
      - データの順序番号　端末起動後計測開始時に 1 から始まり、最小計測単位データの個数分増加していく
        
        Sequential number of data. Starts at 1 when measurement starts after the terminal startup, and increases by the number of minimum measurement unit data.
    * - data_key
      - string
      - 計測データ取得に使用された計器固有のコマンド
        
        Device-specific commands used to acquire this measurement data
    * - data_aux
      - string
      - データに関する補足情報　現在は計器のメーカーとモデル名が格納される
        
        Stores auxiliary information about this data, currently vendor and model names of the target measure.
    * - data_chunk
      - array<json-object>
      - :ref:`最小計測単位 <section-measures-vibration>` の収集計測データが格納される配列
        
        Array stores the collected measurement data in the :ref:`minimum measurement unit <section-measures-vibration>`.
    * - timestamp
      - number
      - 計測データの取得時刻　ミリ秒単位UNIX時刻 (UTC)
        
        Time at which this data entry was acquired. UNIX time in milliseconds (UTC)
    * - Lv
      - number
      - 計測データ取得時の振動最新値
        
        Latest vibration value at this data entry was acquired
    * - Lvmax
      - number
      - 最小計測単位時間内での振動最大値
        
        Maximum vibration value within the minimum measurement unit time
    * - Lvmin
      - number
      - 最小計測単位時間内での振動最小値
        
        Minimum vibration value within the minimum measurement unit time
    * - L5
      - number
      - 最小計測単位時間内での振動L5値
        
        L5 vibration value within the minimum measurement unit time
    * - L10
      - number
      - 最小計測単位時間内での振動L10値
        
        L10 vibration value within the minimum measurement unit time
    * - L50
      - number
      - 最小計測単位時間内での振動L50値
        
        L50 vibration value within the minimum measurement unit time
    * - L90
      - number
      - 最小計測単位時間内での振動L90値
        
        L90 vibration value within the minimum measurement unit time
    * - L95
      - number
      - 最小計測単位時間内での振動L95値
        
        L95 vibration value within the minimum measurement unit time

vibration4/data_chunk
=====================

*Target Measures*
^^^^^^^^^^^^^^^^^

- | アコー [ACO] TYPE3666 内蔵振動計
  | Vibration measure embedded in unit

*Destination IoT Topic*
^^^^^^^^^^^^^^^^^^^^^^^

aws/questar/soshinki/vibration/data_chunk

*Example*
^^^^^^^^^

.. code-block:: json

    {
      "device_id": "SK000010",
      "device_data_type": "vibration4/chunk",
      "data_version": "20250402",
      "data_no": 1,
      "data_key": "as",
      "data_aux": "ACO TYPE3666",
      "data_chunk": [
        {
          "timestamp": 1744269939328,
          "Lv": 25.9
        },
        {
          "timestamp": 1744269940335,
          "Lv": 24.8
        },
        {
          "timestamp": 1744269941343,
          "Lv": 25.7
        },
        {
          "timestamp": 1744269942350,
          "Lv": 25.4
        },
        {
          "timestamp": 1744269943359,
          "Lv": 25.2
        },
        {
          "timestamp": 1744269944368,
          "Lv": 27.2
        },
        {
          "timestamp": 1744269945375,
          "Lv": 25.8
        },
        {
          "timestamp": 1744269946383,
          "Lv": 25.4
        },
        {
          "timestamp": 1744269947327,
          "Lv": 25.9
        },
        {
          "timestamp": 1744269948335,
          "Lv": 26.7
        },
        {
          "timestamp": 1744269949343,
          "Lv": 26.5
        },
        {
          "timestamp": 1744269950352,
          "Lv": 27.2
        }
      ]
    }

*Field Items*
^^^^^^^^^^^^^

.. list-table::
    :header-rows: 1
    :widths: 1, 1, 3

    * - Name
      - Type
      - Description
    * - device_id
      - string
      - 端末固有のID
        
        Unique ID of the terminal which sent this data
    * - device_data_type
      - string
      - :ref:`vibration4 <section-commondefinition-devicetype>`/:ref:`chunk <section-commondefinition-datatype>`
    * - data_version
      - string
      - データ形式のバージョン　データ形式が部分的に変更された場合に本値が更新される
        
        Version of data format. This value will be updated when the data format is partially changed.
    * - data_no
      - number
      - データの順序番号　端末起動後計測開始時に 1 から始まり、最小計測単位データの個数分増加していく
        
        Sequential number of data. Starts at 1 when measurement starts after the terminal startup, and increases by the number of minimum measurement unit data.
    * - data_key
      - string
      - 計測データ取得に使用された計器固有のコマンド
        
        Device-specific commands used to acquire this measurement data
    * - data_aux
      - string
      - データに関する補足情報　現在は計器のメーカーとモデル名が格納される
        
        Stores auxiliary information about this data, currently vendor and model names of the target measure.
    * - data_chunk
      - array<json-object>
      - :ref:`最小計測単位 <section-measures-vibration>` の収集計測データが格納される配列
        
        Array stores the collected measurement data in the :ref:`minimum measurement unit <section-measures-vibration>`.
    * - timestamp
      - number
      - 計測データの取得時刻　ミリ秒単位UNIX時刻 (UTC)
        
        Time at which this data entry was acquired. UNIX time in milliseconds (UTC)
    * - Lv
      - number
      - 計測データ取得時の振動最新値
        
        Latest vibration value at this data entry was acquired

weather1/data_chunk
===================

*Target Measures*
^^^^^^^^^^^^^^^^^

- misol Weather Station WH24C

*Destination IoT Topic*
^^^^^^^^^^^^^^^^^^^^^^^

aws/questar/soshinki/weather/data_chunk

*Example*
^^^^^^^^^

.. code-block:: json

    {
      "device_id": "SK000010",
      "device_data_type": "weather1/chunk",
      "data_version": "20250402",
      "data_no": 1,
      "data_key": "wh",
      "data_aux": "Weather Station WH24C",
      "data_chunk": [
        {
          "timestamp": 1744276729195,
          "wind_speed": 0.0,
          "gust_speed": 0.0,
          "wind_direction": 62,
          "temperature": 16.4,
          "humidity": 69,
          "accumulation_rainfall": 18.9,
          "uv": 0,
          "light": 0
        },
        {
          "timestamp": 1744276745194,
          "wind_speed": 0.0,
          "gust_speed": 0.0,
          "wind_direction": 62,
          "temperature": 16.4,
          "humidity": 69,
          "accumulation_rainfall": 18.9,
          "uv": 0,
          "light": 0
        },
        {
          "timestamp": 1744276761197,
          "wind_speed": 0.0,
          "gust_speed": 0.0,
          "wind_direction": 62,
          "temperature": 16.4,
          "humidity": 69,
          "accumulation_rainfall": 18.9,
          "uv": 0,
          "light": 0
        },
        {
          "timestamp": 1744276777196,
          "wind_speed": 0.0,
          "gust_speed": 0.0,
          "wind_direction": 62,
          "temperature": 16.4,
          "humidity": 69,
          "accumulation_rainfall": 18.9,
          "uv": 0,
          "light": 0
        }
      ]
    }

*Field Items*
^^^^^^^^^^^^^

.. list-table::
    :header-rows: 1
    :widths: 1, 1, 3

    * - Name
      - Type
      - Description
    * - device_id
      - string
      - 端末固有のID
        
        Unique ID of the terminal which sent this data
    * - device_data_type
      - string
      - :ref:`weather1 <section-commondefinition-devicetype>`/:ref:`chunk <section-commondefinition-datatype>`
    * - data_version
      - string
      - データ形式のバージョン　データ形式が部分的に変更された場合に本値が更新される
        
        Version of data format. This value will be updated when the data format is partially changed.
    * - data_no
      - number
      - データの順序番号　端末起動後計測開始時に 1 から始まり、最小計測単位データの個数分増加していく
        
        Sequential number of data. Starts at 1 when measurement starts after the terminal startup, and increases by the number of minimum measurement unit data.
    * - data_key
      - string
      - 計測データ取得に使用された計器固有のコマンド
        
        Device-specific commands used to acquire this measurement data
    * - data_aux
      - string
      - データに関する補足情報　現在は計器のメーカーとモデル名が格納される
        
        Stores auxiliary information about this data, currently vendor and model names of the target measure.
    * - data_chunk
      - array<json-object>
      - :ref:`最小計測単位 <section-measures-weather>` の収集計測データが格納される配列
        
        Array stores the collected measurement data in the :ref:`minimum measurement unit <section-measures-weather>`.
    * - timestamp
      - number
      - 計測データの取得時刻　ミリ秒単位UNIX時刻 (UTC)
        
        Time at which this data entry was acquired. UNIX time in milliseconds (UTC)
    * - wind_speed
      - number
      - 計測データ取得時の風速値
        
        Wind speed value at this data entry was acquired
    * - gust_speed
      - number
      - 計測データ取得時の瞬間風速値
        
        Wind gust speed value at this data entry was acquired
    * - wind_direction
      - number
      - 計測データ取得時の風向値
        
        Wind direction value at this data entry was acquired
    * - temperature
      - number
      - 計測データ取得時の温度値
        
        Temperature value at this data entry was acquired
    * - humidity
      - number
      - 計測データ取得時の湿度値
        
        Humidity value at this data entry was acquired
    * - accumulation_rainfall
      - number
      - 計測データ取得時の積算雨量値
        
        Accumulation rainfall value at this data entry was acquired
    * - uv
      - number
      - 計測データ取得時の紫外線量値
        
        UV index value at this data entry was acquired
    * - light
      - number
      - 計測データ取得時の光照度値
        
        Light illuminance value at this data entry was acquired

.. _section-iottopicmessages-datasum:

noise1/data_sum
===============

*Target Measures*
^^^^^^^^^^^^^^^^^

- リオン [RION] NL-42A

*Destination IoT Topic*
^^^^^^^^^^^^^^^^^^^^^^^

aws/questar/soshinki/noise/data_sum

*Example*
^^^^^^^^^

.. code-block:: json

    {
      "device_id": "SK000010",
      "device_data_type": "noise1/sum",
      "data_version": "20250402",
      "data_no": 1,
      "data_key": "dod",
      "data_aux": "RION NL-42A",
      "data_sum": {
        "timestamp": 1744262065473,
        "noise_latest": 66.2,
        "noise_average": 69.1,
        "noise_l5": 73.65,
        "noise_l10": 73.4,
        "noise_l50": 69.8,
        "noise_l90": 61.7,
        "noise_l95": 60.0,
        "noise_max": 73.8,
        "noise_max_time": 1744262061467,
        "noise_min": 66.2,
        "noise_min_time": 1744262062468
      }
    }

*Field Items*
^^^^^^^^^^^^^

.. list-table::
    :header-rows: 1
    :widths: 1, 1, 3

    * - Name
      - Type
      - Description
    * - device_id
      - string
      - 端末固有のID
        
        Unique ID of the terminal which sent this data
    * - device_data_type
      - string
      - :ref:`noise1 <section-commondefinition-devicetype>`/:ref:`sum <section-commondefinition-datatype>`
    * - data_version
      - string
      - データ形式のバージョン　データ形式が部分的に変更された場合に本値が更新される
        
        Version of data format. This value will be updated when the data format is partially changed.
    * - data_no
      - number
      - データの順序番号　端末起動後計測開始時に 1 から始まり、最小計測単位データの個数分増加していく
        
        Sequential number of data. Starts at 1 when measurement starts after the terminal startup, and increases by the number of minimum measurement unit data.
    * - data_key
      - string
      - 計測データ取得に使用された計器固有のコマンド
        
        Device-specific commands used to acquire this measurement data
    * - data_aux
      - string
      - データに関する補足情報　現在は計器のメーカーとモデル名が格納される
        
        Stores auxiliary information about this data, currently vendor and model names of the target measure.
    * - data_sum
      - json-object
      - :ref:`最小集計単位 <section-measures-noise>` の計測データが格納される
        
        Stores measurement data in the :ref:`minimum aggregation unit <section-measures-noise>`.
    * - timestamp
      - number
      - 計測データの取得時刻　ミリ秒単位UNIX時刻 (UTC)
        
        Time at which this data was acquired. UNIX time in milliseconds (UTC)
    * - noise_latest
      - number
      - 計測データ取得時の騒音最新値
        
        Latest noise value at this data was acquired
    * - noise_average
      - number
      - 最小集計単位時間内での騒音平均値
        
        Average noise value within the minimum aggregation unit time
    * - noise_l5
      - number
      - 最小集計単位時間内での騒音L5値
        
        L5 noise value within the minimum aggregation unit time
    * - noise_l10
      - number
      - 最小集計単位時間内での騒音L10値
        
        L10 noise value within the minimum aggregation unit time
    * - noise_l50
      - number
      - 最小集計単位時間内での騒音L50値
        
        L50 noise value within the minimum aggregation unit time
    * - noise_l90
      - number
      - 最小集計単位時間内での騒音L90値
        
        L90 noise value within the minimum aggregation unit time
    * - noise_l95
      - number
      - 最小集計単位時間内での騒音L95値
        
        L95 noise value within the minimum aggregation unit time
    * - noise_max
      - number
      - 最小集計単位内での騒音最大値
        
        Maximum noise value within the minimum aggregation unit time
    * - noise_max_time
      - number
      - noise_max 値の取得時刻　ミリ秒単位UNIX時刻 (UTC)
        
        Time at which the noise_max value was acquired. UNIX time in milliseconds (UTC)
    * - noise_min
      - number
      - 最小集計単位時間内での騒音最小値
        
        Minimum noise value within the minimum aggregation unit time
    * - noise_max_time
      - number
      - noise_min 値の取得時刻　ミリ秒単位UNIX時刻 (UTC)
        
        Time at which the noise_min value was acquired. UNIX time in milliseconds (UTC)

noise2/data_sum
===============

*Target Measures*
^^^^^^^^^^^^^^^^^

- リオン [RION] NL-43

*Destination IoT Topic*
^^^^^^^^^^^^^^^^^^^^^^^

aws/questar/soshinki/noise/data_sum

*Example*
^^^^^^^^^

.. code-block:: json

    {
      "device_id": "SK000010",
      "device_data_type": "noise2/sum",
      "data_version": "20250402",
      "data_no": 1,
      "data_key": "dod",
      "data_aux": "RION NL-43",
      "data_sum": {
        "timestamp": 1744262301017,
        "noise_latest": 63.9,
        "noise_average": 62.7,
        "noise_l5": 75.5,
        "noise_l10": 74.15,
        "noise_l50": 70.95,
        "noise_l90": 57.25,
        "noise_l95": 55.4,
        "noise_max": 73.4,
        "noise_max_time": 1744262294008,
        "noise_min": 51.3,
        "noise_min_time": 1744262298013
      }
    }

*Field Items*
^^^^^^^^^^^^^

.. list-table::
    :header-rows: 1
    :widths: 1, 1, 3

    * - Name
      - Type
      - Description
    * - device_id
      - string
      - 端末固有のID
        
        Unique ID of the terminal which sent this data
    * - device_data_type
      - string
      - :ref:`noise2 <section-commondefinition-devicetype>`/:ref:`sum <section-commondefinition-datatype>`
    * - data_version
      - string
      - データ形式のバージョン　データ形式が部分的に変更された場合に本値が更新される
        
        Version of data format. This value will be updated when the data format is partially changed.
    * - data_no
      - number
      - データの順序番号　端末起動後計測開始時に 1 から始まり、最小計測単位データの個数分増加していく
        
        Sequential number of data. Starts at 1 when measurement starts after the terminal startup, and increases by the number of minimum measurement unit data.
    * - data_key
      - string
      - 計測データ取得に使用された計器固有のコマンド
        
        Device-specific commands used to acquire this measurement data
    * - data_aux
      - string
      - データに関する補足情報　現在は計器のメーカーとモデル名が格納される
        
        Stores auxiliary information about this data, currently vendor and model names of the target measure.
    * - data_sum
      - json-object
      - :ref:`最小集計単位 <section-measures-noise>` の計測データが格納される
        
        Stores measurement data in the :ref:`minimum aggregation unit <section-measures-noise>`.
    * - timestamp
      - number
      - 計測データの取得時刻　ミリ秒単位UNIX時刻 (UTC)
        
        Time at which this data was acquired. UNIX time in milliseconds (UTC)
    * - noise_latest
      - number
      - 計測データ取得時の騒音最新値
        
        Latest noise value at this data was acquired
    * - noise_average
      - number
      - 最小集計単位時間内での騒音平均値
        
        Average noise value within the minimum aggregation unit time
    * - noise_l5
      - number
      - 最小集計単位時間内での騒音L5値
        
        L5 noise value within the minimum aggregation unit time
    * - noise_l10
      - number
      - 最小集計単位時間内での騒音L10値
        
        L10 noise value within the minimum aggregation unit time
    * - noise_l50
      - number
      - 最小集計単位時間内での騒音L50値
        
        L50 noise value within the minimum aggregation unit time
    * - noise_l90
      - number
      - 最小集計単位時間内での騒音L90値
        
        L90 noise value within the minimum aggregation unit time
    * - noise_l95
      - number
      - 最小集計単位時間内での騒音L95値
        
        L95 noise value within the minimum aggregation unit time
    * - noise_max
      - number
      - 最小集計単位内での騒音最大値
        
        Maximum noise value within the minimum aggregation unit time
    * - noise_max_time
      - number
      - noise_max 値の取得時刻　ミリ秒単位UNIX時刻 (UTC)
        
        Time at which the noise_max value was acquired. UNIX time in milliseconds (UTC)
    * - noise_min
      - number
      - 最小集計単位時間内での騒音最小値
        
        Minimum noise value within the minimum aggregation unit time
    * - noise_max_time
      - number
      - noise_min 値の取得時刻　ミリ秒単位UNIX時刻 (UTC)
        
        Time at which the noise_min value was acquired. UNIX time in milliseconds (UTC)

.. NOTE ::

    | `noise2/data_sum`_ は `noise1/data_sum`_ と同一形式
    | `noise2/data_sum`_ has same format as `noise1/data_sum`_.

noise4/data_sum
===============

*Target Measures*
^^^^^^^^^^^^^^^^^

- | アコー [ACO] TYPE3666 内蔵騒音計
  | Noise measure embedded in unit

*Destination IoT Topic*
^^^^^^^^^^^^^^^^^^^^^^^

aws/questar/soshinki/noise/data_sum

*Example*
^^^^^^^^^

.. code-block:: json

    {
      "device_id": "SK000010",
      "device_data_type": "noise4/sum",
      "data_version": "20250402",
      "data_no": 1,
      "data_key": "as",
      "data_aux": "ACO TYPE3666",
      "data_sum": {
        "timestamp": 1744269806379,
        "noise_latest": 53.4,
        "noise_average": 47.9,
        "noise_l5": 53.4,
        "noise_l10": 52.1,
        "noise_l50": 48.55,
        "noise_l90": 43.7,
        "noise_l95": 41.3,
        "noise_max": 56.5,
        "noise_max_time": 1744269805403,
        "noise_min": 41.0,
        "noise_min_time": 1744269803387
      }
    }

*Field Items*
^^^^^^^^^^^^^

.. list-table::
    :header-rows: 1
    :widths: 1, 1, 3

    * - Name
      - Type
      - Description
    * - device_id
      - string
      - 端末固有のID
        
        Unique ID of the terminal which sent this data
    * - device_data_type
      - string
      - :ref:`noise4 <section-commondefinition-devicetype>`/:ref:`sum <section-commondefinition-datatype>`
    * - data_version
      - string
      - データ形式のバージョン　データ形式が部分的に変更された場合に本値が更新される
        
        Version of data format. This value will be updated when the data format is partially changed.
    * - data_no
      - number
      - データの順序番号　端末起動後計測開始時に 1 から始まり、最小計測単位データの個数分増加していく
        
        Sequential number of data. Starts at 1 when measurement starts after the terminal startup, and increases by the number of minimum measurement unit data.
    * - data_key
      - string
      - 計測データ取得に使用された計器固有のコマンド
        
        Device-specific commands used to acquire this measurement data
    * - data_aux
      - string
      - データに関する補足情報　現在は計器のメーカーとモデル名が格納される
        
        Stores auxiliary information about this data, currently vendor and model names of the target measure.
    * - data_sum
      - json-object
      - :ref:`最小集計単位 <section-measures-noise>` の計測データが格納される
        
        Stores measurement data in the :ref:`minimum aggregation unit <section-measures-noise>`.
    * - timestamp
      - number
      - 計測データの取得時刻　ミリ秒単位UNIX時刻 (UTC)
        
        Time at which this data was acquired. UNIX time in milliseconds (UTC)
    * - noise_latest
      - number
      - 計測データ取得時の騒音最新値
        
        Latest noise value at this data was acquired
    * - noise_average
      - number
      - 最小集計単位時間内での騒音平均値
        
        Average noise value at this data was acquired
    * - noise_l5
      - number
      - 最小集計単位時間内での騒音L5値
        
        L5 noise value within the minimum aggregation unit time
    * - noise_l10
      - number
      - 最小集計単位時間内での騒音L10値
        
        L10 noise value within the minimum aggregation unit time
    * - noise_l50
      - number
      - 最小集計単位内での騒音L50値
        
        L50 noise value within the minimum aggregation unit time
    * - noise_l90
      - number
      - 最小集計単位時間内での騒音L90値
        
        L90 noise value within the minimum aggregation unit time
    * - noise_l95
      - number
      - 最小集計単位内での騒音L95値
        
        L95 noise value within the minimum aggregation unit time
    * - noise_max
      - number
      - 最小集計単位時間内での騒音最大値
        
        Maximum noise value within the minimum aggregation unit time
    * - noise_max_time
      - number
      - noise_max 値の取得時刻　ミリ秒単位UNIX時刻 (UTC)
        
        Time at which the vibration_max value was acquired. UNIX time in milliseconds (UTC)
    * - noise_min
      - number
      - 最小集計単位時間内での騒音最小値
        
        Minimum noise value within the minimum aggregation unit time
    * - noise_max_time
      - number
      - noise_min 値の取得時刻　ミリ秒単位UNIX時刻 (UTC)
        
        Time at which the vibration_min value was acquired. UNIX time in milliseconds (UTC)

.. NOTE ::

    | `noise4/data_sum`_ は `noise1/data_sum`_ と同一形式
    | `noise4/data_sum`_ has same format as `noise1/data_sum`_.

vibration1/data_sum
===================

*Target Measures*
^^^^^^^^^^^^^^^^^

- リオン [RION] VM-55

*Destination IoT Topic*
^^^^^^^^^^^^^^^^^^^^^^^

aws/questar/soshinki/vibration/data_sum

*Example*
^^^^^^^^^

.. code-block:: json

    {
      "device_id": "SK000010",
      "device_data_type": "vibration1/sum",
      "data_version": "20250402",
      "data_no": 1,
      "data_key": "dod",
      "data_aux": "RION VM-55",
      "data_sum": {
        "timestamp": 1744262463739,
        "vibration_latest": 31.9,
        "vibration_average": 32.0,
        "vibration_l5": 33.6,
        "vibration_l10": 33.4,
        "vibration_l50": 31.55,
        "vibration_l90": 30.5,
        "vibration_l95": 30.3,
        "vibration_max": 33.6,
        "vibration_max_time": 1744262458730,
        "vibration_min": 30.3,
        "vibration_min_time": 1744262454723
      }
    }

*Field Items*
^^^^^^^^^^^^^

.. list-table::
    :header-rows: 1
    :widths: 1, 1, 3

    * - Name
      - Type
      - Description
    * - device_id
      - string
      - 端末固有のID
        
        Unique ID of the terminal which sent this data
    * - device_data_type
      - string
      - :ref:`vibration1 <section-commondefinition-devicetype>`/:ref:`sum <section-commondefinition-datatype>`
    * - data_version
      - string
      - データ形式のバージョン　データ形式が部分的に変更された場合に本値が更新される
        
        Version of data format. This value will be updated when the data format is partially changed.
    * - data_no
      - number
      - データの順序番号　端末起動後計測開始時に 1 から始まり、最小計測単位データの個数分増加していく
        
        Sequential number of data. Starts at 1 when measurement starts after the terminal startup, and increases by the number of minimum measurement unit data.
    * - data_key
      - string
      - 計測データ取得に使用された計器固有のコマンド
        
        Device-specific commands used to acquire this measurement data
    * - data_aux
      - string
      - データに関する補足情報　現在は計器のメーカーとモデル名が格納される
        
        Stores auxiliary information about this data, currently vendor and model names of the target measure.
    * - data_sum
      - json-object
      - :ref:`最小集計単位 <section-measures-vibration>` の計測データが格納される
        
        Stores measurement data in the :ref:`minimum aggregation unit <section-measures-vibration>`.
    * - timestamp
      - number
      - 計測データの取得時刻　ミリ秒単位UNIX時刻 (UTC)
        
        Time at which this data was acquired. UNIX time in milliseconds (UTC)
    * - vibration_latest
      - number
      - 計測データ取得時の振動最新値
        
        Latest vibration value at this data was acquired
    * - vibration_average
      - number
      - 最小集計単位時間内での振動平均値
        
        Average vibration value within the minimum aggregation unit time
    * - vibration_l5
      - number
      - 最小集計単位時間内での振動L5値
        
        L5 vibration value within the minimum aggregation unit time
    * - vibration_l10
      - number
      - 最小集計単位時間内での振動L10値
        
        L10 vibration value within the minimum aggregation unit time
    * - vibration_l50
      - number
      - 最小集計単位時間内での振動L50値
        
        L50 vibration value within the minimum aggregation unit time
    * - vibration_l90
      - number
      - 最小集計単位時間内での振動L90値
        
        L90 vibration value within the minimum aggregation unit time
    * - vibration_l95
      - number
      - 最小集計単位時間内での振動L95値
        
        L95 vibration value within the minimum aggregation unit time
    * - vibration_max
      - number
      - 最小集計単位時間内での振動最大値
        
        Maximum vibration value within the minimum aggregation unit time
    * - vibration_max_time
      - number
      - vibration_max 値の取得時刻　ミリ秒単位UNIX時刻 (UTC)
        
        Time at which the vibration_max value was acquired. UNIX time in milliseconds (UTC)
    * - vibration_min
      - number
      - 最小集計単位時間内での振動最小値
        
        Minimum vibration value within the minimum aggregation unit time
    * - vibration_min_time
      - number
      - vibration_min 値の取得時刻　ミリ秒単位UNIX時刻 (UTC)
        
        Time at which the vibration_min value was acquired. UNIX time in milliseconds (UTC)

vibration4/data_sum
===================

*Target Measures*
^^^^^^^^^^^^^^^^^

- | アコー [ACO] TYPE3666 内蔵振動計
  | Vibration measure embedded in unit

*Destination IoT Topic*
^^^^^^^^^^^^^^^^^^^^^^^

aws/questar/soshinki/vibration/data_sum

*Example*
^^^^^^^^^

.. code-block:: json

    {
      "device_id": "SK000010",
      "device_data_type": "vibration4/sum",
      "data_version": "20250402",
      "data_no": 1,
      "data_key": "as",
      "data_aux": "ACO TYPE3666",
      "data_sum": {
        "timestamp": 1744269950352,
        "vibration_latest": 27.2,
        "vibration_average": 26.0,
        "vibration_l5": 27.2,
        "vibration_l10": 26.7,
        "vibration_l50": 25.85,
        "vibration_l90": 25.4,
        "vibration_l95": 25.2,
        "vibration_max": 27.2,
        "vibration_max_time": 1744269944368,
        "vibration_min": 24.8,
        "vibration_min_time": 1744269940335
      }
    }

*Field Items*
^^^^^^^^^^^^^

.. list-table::
    :header-rows: 1
    :widths: 1, 1, 3

    * - Name
      - Type
      - Description
    * - device_id
      - string
      - 端末固有のID
        
        Unique ID of the terminal which sent this data
    * - device_data_type
      - string
      - :ref:`vibration4 <section-commondefinition-devicetype>`/:ref:`sum <section-commondefinition-datatype>`
    * - data_version
      - string
      - データ形式のバージョン　データ形式が部分的に変更された場合に本値が更新される
        
        Version of data format. This value will be updated when the data format is partially changed.
    * - data_no
      - number
      - データの順序番号　端末起動後計測開始時に 1 から始まり、最小計測単位データの個数分増加していく
        
        Sequential number of data. Starts at 1 when measurement starts after the terminal startup, and increases by the number of minimum measurement unit data.
    * - data_key
      - string
      - 計測データ取得に使用された計器固有のコマンド
        
        Device-specific commands used to acquire this measurement data
    * - data_aux
      - string
      - データに関する補足情報　現在は計器のメーカーとモデル名が格納される
        
        Stores auxiliary information about this data, currently vendor and model names of the target measure.
    * - data_sum
      - json-object
      - :ref:`最小集計単位 <section-measures-vibration>` の計測データが格納される
        
        Stores measurement data in the :ref:`minimum aggregation unit <section-measures-vibration>`.
    * - timestamp
      - number
      - 計測データの取得時刻　ミリ秒単位UNIX時刻 (UTC)
        
        Time at which this data was acquired. UNIX time in milliseconds (UTC)
    * - vibration_latest
      - number
      - 計測データ取得時の振動最新値
        
        Latest vibration value at this data was acquired
    * - vibration_average
      - number
      - 最小集計単位時間内での振動平均値
        
        Average vibration value within the minimum aggregation unit time
    * - vibration_l5
      - number
      - 最小集計単位時間内での振動L5値
        
        L5 vibration value within the minimum aggregation unit time
    * - vibration_l10
      - number
      - 最小集計単位時間内での振動L10値
        
        L10 vibration value within the minimum aggregation unit time
    * - vibration_l50
      - number
      - 最小集計単位時間内での振動L50値
        
        L50 vibration value within the minimum aggregation unit time
    * - vibration_l90
      - number
      - 最小集計単位時間内での振動L90値
        
        L90 vibration value within the minimum aggregation unit time
    * - vibration_l95
      - number
      - 最小集計単位時間内での振動L95値
        
        L95 vibration value within the minimum aggregation unit time
    * - vibration_max
      - number
      - 最小集計単位時間内での振動最大値
        
        Maximum vibration value within the minimum aggregation unit time
    * - vibration_max_time
      - number
      - vibration_max 値の取得時刻　ミリ秒単位UNIX時刻 (UTC)
        
        Time at which the vibration_max value was acquired. UNIX time in milliseconds (UTC)
    * - vibration_min
      - number
      - 最小集計単位時間内での振動最小値
        
        Minimum vibration value within the minimum aggregation unit time
    * - vibration_min_time
      - number
      - vibration_min 値の取得時刻　ミリ秒単位UNIX時刻 (UTC)
        
        Time at which the vibration_min value was acquired. UNIX time in milliseconds (UTC)

.. NOTE ::

    | `vibration4/data_sum`_ は `vibration1/data_sum`_ と同一形式
    | `vibration4/data_sum`_ has same format as `vibration1/data_sum`_.

weather1/data_sum
=================

*Target Measures*
^^^^^^^^^^^^^^^^^

- misol Weather Station WH24C

*Destination IoT Topic*
^^^^^^^^^^^^^^^^^^^^^^^

aws/questar/soshinki/weather/data_sum

*Example*
^^^^^^^^^

.. code-block:: json

    {
      "device_id": "SK000010",
      "device_data_type": "weather1/sum",
      "data_version": "20250402",
      "data_no": 1,
      "data_key": "wh",
      "data_aux": "Weather Station WH24C",
      "data_sum": {
        "timestamp": 1744276777196,
        "wind_speed_latest": 0.0,
        "wind_speed_average": 0.0,
        "wind_speed_l50": 0.0,
        "wind_speed_max": 0.0,
        "wind_speed_max_time": 1744276729195,
        "wind_speed_min": 0.0,
        "wind_speed_min_time": 1744276729195,
        "gust_speed_latest": 0.0,
        "gust_speed_l50": 0.0,
        "wind_direction_latest": 62,
        "wind_direction_l50": 62,
        "temperature_latest": 16.4,
        "temperature_l50": 16.4,
        "humidity_latest": 69,
        "humidity_l50": 69,
        "accumulation_rainfall_latest": 18.9,
        "accumulation_rainfall_l50": 18.9,
        "uv_latest": 0,
        "uv_l50": 0,
        "light_latest": 0,
        "light_l50": 0
      }
    }

*Field Items*
^^^^^^^^^^^^^

.. list-table::
    :header-rows: 1
    :widths: 1, 1, 3

    * - Name
      - Type
      - Description
    * - device_id
      - string
      - 端末固有のID
        
        Unique ID of the terminal which sent this data
    * - device_data_type
      - string
      - :ref:`weather1 <section-commondefinition-devicetype>`/:ref:`sum <section-commondefinition-datatype>`
    * - data_version
      - string
      - データ形式のバージョン　データ形式が部分的に変更された場合に本値が更新される
        
        Version of data format. This value will be updated when the data format is partially changed.
    * - data_no
      - number
      - データの順序番号　端末起動後計測開始時に 1 から始まり、最小計測単位データの個数分増加していく
        
        Sequential number of data. Starts at 1 when measurement starts after the terminal startup, and increases by the number of minimum measurement unit data.
    * - data_key
      - string
      - 計測データ取得に使用された計器固有のコマンド
        
        Device-specific commands used to acquire this measurement data
    * - data_aux
      - string
      - データに関する補足情報　現在は計器のメーカーとモデル名が格納される
        
        Stores auxiliary information about this data, currently vendor and model names of the target measure.
    * - data_sum
      - json-object
      - :ref:`最小集計単位 <section-measures-weather>` の計測データが格納される
        
        Stores measurement data in the :ref:`minimum aggregation unit <section-measures-weather>`.
    * - timestamp
      - number
      - 計測データの取得時刻　ミリ秒単位UNIX時刻 (UTC)
        
        Time at which this data was acquired. UNIX time in milliseconds (UTC)
    * - wind_speed_latest
      - number
      - 計測データ取得時の風速最新値
        
        Latest wind speed value at this data was acquired
    * - wind_speed_average
      - number
      - 最小集計単位時間内での風速平均値
        
        Average wind speed value within the minimum aggregation unit time
    * - wind_speed_l50
      - number
      - 最小集計単位時間内での風速L50値
        
        L50 wind speed value within the minimum aggregation unit time
    * - wind_speed_max
      - number
      - 最小集計単位時間内での風速最大値
        
        Maximum wind speed value within the minimum aggregation unit time
    * - wind_speed_max_time
      - number
      - wind_speed_max 値の取得時刻　ミリ秒単位UNIX時刻 (UTC)
        
        Time at which the wind_speed_max value was acquired. UNIX time in milliseconds (UTC)
    * - wind_speed_min
      - number
      - 最小集計単位時間内での風速最小値
        
        Minimum wind speed value within the minimum aggregation unit time
    * - wind_speed_min_time
      - number
      - wind_speed_min 値の取得時刻　ミリ秒単位UNIX時刻 (UTC)
        
        Time at which the wind_speed_min value was acquired. UNIX time in milliseconds (UTC)
    * - gust_speed_latest
      - number
      - 計測データ取得時の瞬間風速最新値
        
        Latest wind gust speed value at this data was acquired
    * - gust_speed_l50
      - number
      - 最小集計単位時間内での瞬間風速L50値
        
        L50 wind gust speed value within the minimum aggregation unit time
    * - wind_direction_latest
      - number
      - 計測データ取得時の風向最新値
        
        Latest wind direction value at this data was acquired
    * - wind_direction_l50
      - number
      - 最小集計単位時間内での風向L50値
        
        L50 wind direction value within the minimum aggregation unit time
    * - temperature_latest
      - number
      - 計測データ取得時の温度最新値
        
        Latest temperature value at this data was acquired
    * - temperature_l50
      - number
      - 最小集計単位時間内での温度L50値
        
        L50 temperature value within the minimum aggregation unit time
    * - humidity_latest
      - number
      - 計測データ取得時の湿度最新値
        
        Latest humidity value at this data was acquired
    * - humidity_l50
      - number
      - 最小集計単位時間内での湿度L50値
        
        L50 humidity value within the minimum aggregation unit time
    * - accumulation_rainfall_latest
      - number
      - 計測データ取得時の積算雨量最新値
        
        Latest accumulation rainfall value at this data was acquired
    * - accumulation_rainfall_l50
      - number
      - 最小集計単位時間内での積算雨量L50値
        
        L50 accumulation rainfall value within the minimum aggregation unit time
    * - uv_latest
      - number
      - 計測データ取得時の紫外線量最新値
        
        Latest UV index value at this data was acquired
    * - uv_l50
      - number
      - 最小集計単位時間内での紫外線L50値
        
        L50 UV index value within the minimum aggregation unit time
    * - light_latest
      - number
      - 計測データ取得時の光照度最新値
        
        Latest light illuminance value at this data was acquired
    * - light_l50
      - number
      - 最小集計単位時間内での光照度L50値
        
        L50 light illuminance value within the minimum aggregation unit time

.. NOTE ::

    | L50は最小集計時間内での中央値を表しています
    | L50 means median value within the minimum aggregation unit time.

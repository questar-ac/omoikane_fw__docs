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
      "data_version": "20250502",
      "data_no": 1,
      "data_key": "dod",
      "data_aux": [
        "RION NL-42A"
      ],
      "data_chunk": [
        {
          "timestamp": 1746137273928,
          "Lp": 63.3,
          "Lmax": 67.9,
          "Lmin": 64.4,
          "L5": 67.6,
          "L10": 67.6,
          "L50": 66.8,
          "L90": 64.8,
          "L95": 64.4
        },
        {
          "timestamp": 1746137274929,
          "Lp": 65.9,
          "Lmax": 67.9,
          "Lmin": 61.5,
          "L5": 67.6,
          "L10": 67.4,
          "L50": 65.8,
          "L90": 62.8,
          "L95": 62.5
        },
        {
          "timestamp": 1746137275931,
          "Lp": 65.6,
          "Lmax": 75.1,
          "Lmin": 61.5,
          "L5": 74.1,
          "L10": 73.6,
          "L50": 66.8,
          "L90": 63.0,
          "L95": 62.5
        },
        {
          "timestamp": 1746137276932,
          "Lp": 45.0,
          "Lmax": 75.1,
          "Lmin": 48.0,
          "L5": 74.1,
          "L10": 72.5,
          "L50": 65.8,
          "L90": 60.0,
          "L95": 53.8
        },
        {
          "timestamp": 1746137277933,
          "Lp": 72.6,
          "Lmax": 78.3,
          "Lmin": 44.7,
          "L5": 76.0,
          "L10": 74.6,
          "L50": 66.5,
          "L90": 60.0,
          "L95": 50.9
        },
        {
          "timestamp": 1746137278936,
          "Lp": 61.3,
          "Lmax": 78.3,
          "Lmin": 44.7,
          "L5": 76.0,
          "L10": 74.5,
          "L50": 66.3,
          "L90": 53.8,
          "L95": 50.4
        },
        {
          "timestamp": 1746137279938,
          "Lp": 68.2,
          "Lmax": 78.3,
          "Lmin": 44.7,
          "L5": 76.0,
          "L10": 74.5,
          "L50": 66.3,
          "L90": 56.8,
          "L95": 50.4
        },
        {
          "timestamp": 1746137280937,
          "Lp": 63.1,
          "Lmax": 78.3,
          "Lmin": 44.7,
          "L5": 76.0,
          "L10": 74.4,
          "L50": 65.9,
          "L90": 57.3,
          "L95": 50.9
        },
        {
          "timestamp": 1746137281939,
          "Lp": 74.1,
          "Lmax": 79.1,
          "Lmin": 44.7,
          "L5": 76.0,
          "L10": 74.5,
          "L50": 66.3,
          "L90": 59.9,
          "L95": 50.9
        },
        {
          "timestamp": 1746137282940,
          "Lp": 73.9,
          "Lmax": 83.2,
          "Lmin": 44.7,
          "L5": 78.5,
          "L10": 76.2,
          "L50": 67.0,
          "L90": 60.0,
          "L95": 53.8
        }
      ]
    }

*JOSN Object Items*
^^^^^^^^^^^^^^^^^^^

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
      - array<string>
      - データに関する補足情報　現在は計器のメーカーとモデル名が格納される
        
        Stores auxiliary information about this data, currently vendor and model names of the target measure.
    * - data_chunk
      - array<json-object>
      - :ref:`最小計測単位 <section-measureparameters-noise>` の収集計測データが格納される配列
        
        Array stores the collected measurement data in the :ref:`minimum measurement unit <section-measureparameters-noise>`.
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
      "data_version": "20250502",
      "data_no": 1,
      "data_key": "dod",
      "data_aux": [
        "RION NL-43"
      ],
      "data_chunk": [
        {
          "timestamp": 1746139314297,
          "Lp": 70.5,
          "Lmax": 80.4,
          "Lmin": 66.9,
          "L5": 80.1,
          "L10": 78.8,
          "L50": 73.9,
          "L90": 69.9,
          "L95": 67.9
        },
        {
          "timestamp": 1746139315364,
          "Lp": 76.6,
          "Lmax": 80.4,
          "Lmin": 66.9,
          "L5": 78.8,
          "L10": 78.2,
          "L50": 73.9,
          "L90": 70.4,
          "L95": 67.9
        },
        {
          "timestamp": 1746139316302,
          "Lp": 78.6,
          "Lmax": 80.4,
          "Lmin": 66.9,
          "L5": 78.8,
          "L10": 78.2,
          "L50": 73.9,
          "L90": 69.9,
          "L95": 68.3
        },
        {
          "timestamp": 1746139317304,
          "Lp": 74.5,
          "Lmax": 82.2,
          "Lmin": 66.9,
          "L5": 81.0,
          "L10": 80.1,
          "L50": 75.1,
          "L90": 70.4,
          "L95": 68.3
        },
        {
          "timestamp": 1746139318305,
          "Lp": 75.0,
          "Lmax": 82.2,
          "Lmin": 66.9,
          "L5": 81.0,
          "L10": 78.8,
          "L50": 75.2,
          "L90": 70.5,
          "L95": 69.8
        },
        {
          "timestamp": 1746139319306,
          "Lp": 77.4,
          "Lmax": 82.2,
          "Lmin": 66.9,
          "L5": 80.1,
          "L10": 78.6,
          "L50": 75.3,
          "L90": 70.8,
          "L95": 69.8
        },
        {
          "timestamp": 1746139320308,
          "Lp": 76.6,
          "Lmax": 82.2,
          "Lmin": 66.9,
          "L5": 80.1,
          "L10": 78.4,
          "L50": 75.5,
          "L90": 70.8,
          "L95": 69.9
        },
        {
          "timestamp": 1746139321308,
          "Lp": 72.9,
          "Lmax": 82.2,
          "Lmin": 66.9,
          "L5": 80.1,
          "L10": 78.2,
          "L50": 75.5,
          "L90": 71.2,
          "L95": 69.9
        },
        {
          "timestamp": 1746139322312,
          "Lp": 73.1,
          "Lmax": 82.2,
          "Lmin": 66.9,
          "L5": 80.1,
          "L10": 78.6,
          "L50": 75.6,
          "L90": 71.7,
          "L95": 70.4
        },
        {
          "timestamp": 1746139323314,
          "Lp": 75.2,
          "Lmax": 82.2,
          "Lmin": 66.9,
          "L5": 80.1,
          "L10": 78.4,
          "L50": 75.7,
          "L90": 71.9,
          "L95": 70.4
        }
      ]
    }

*JOSN Object Items*
^^^^^^^^^^^^^^^^^^^

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
      - array<string>
      - データに関する補足情報　現在は計器のメーカーとモデル名が格納される
        
        Stores auxiliary information about this data, currently vendor and model names of the target measure.
    * - data_chunk
      - array<json-object>
      - :ref:`最小計測単位 <section-measureparameters-noise>` の収集計測データが格納される配列
        
        Array stores the collected measurement data in the :ref:`minimum measurement unit <section-measureparameters-noise>`.
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
  | Noise measure built-in unit

*Destination IoT Topic*
^^^^^^^^^^^^^^^^^^^^^^^

aws/questar/soshinki/noise/data_chunk

*Example*
^^^^^^^^^

.. code-block:: json

    {
      "device_id": "SK000010",
      "device_data_type": "noise4/chunk",
      "data_version": "20250502",
      "data_no": 1,
      "data_key": "as",
      "data_aux": [
        "ACO TYPE3666"
      ],
      "data_chunk": [
        {
          "timestamp": 1746137948290,
          "Lp": 59.3
        },
        {
          "timestamp": 1746137949329,
          "Lp": 66.7
        },
        {
          "timestamp": 1746137950306,
          "Lp": 62.8
        },
        {
          "timestamp": 1746137951280,
          "Lp": 67.6
        },
        {
          "timestamp": 1746137952325,
          "Lp": 62.4
        },
        {
          "timestamp": 1746137953294,
          "Lp": 58.1
        },
        {
          "timestamp": 1746137954268,
          "Lp": 61.1
        },
        {
          "timestamp": 1746137955303,
          "Lp": 53.0
        },
        {
          "timestamp": 1746137956278,
          "Lp": 46.1
        },
        {
          "timestamp": 1746137957315,
          "Lp": 50.6
        },
        {
          "timestamp": 1746137958289,
          "Lp": 53.3
        },
        {
          "timestamp": 1746137959264,
          "Lp": 61.0
        }
      ]
    }

*JOSN Object Items*
^^^^^^^^^^^^^^^^^^^

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
      - array<string>
      - データに関する補足情報　現在は計器のメーカーとモデル名が格納される
        
        Stores auxiliary information about this data, currently vendor and model names of the target measure.
    * - data_chunk
      - array<json-object>
      - :ref:`最小計測単位 <section-measureparameters-noise>` の収集計測データが格納される配列
        
        Array stores the collected measurement data in the :ref:`minimum measurement unit <section-measureparameters-noise>`.
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
      "data_version": "20250502",
      "data_no": 1,
      "data_key": "dod",
      "data_aux": [
        "RION VM-55"
      ],
      "data_chunk": [
        {
          "timestamp": 1746137464509,
          "Lv": 68.5,
          "Lvmax": 72.6,
          "Lvmin": 65.7,
          "L5": 72.5,
          "L10": 72.5,
          "L50": 71.1,
          "L90": 66.8,
          "L95": 66.1
        },
        {
          "timestamp": 1746137465512,
          "Lv": 69.7,
          "Lvmax": 74.5,
          "Lvmin": 65.7,
          "L5": 74.2,
          "L10": 73.9,
          "L50": 71.7,
          "L90": 68.5,
          "L95": 66.8
        },
        {
          "timestamp": 1746137466514,
          "Lv": 74.3,
          "Lvmax": 74.5,
          "Lvmin": 65.7,
          "L5": 73.9,
          "L10": 73.6,
          "L50": 71.1,
          "L90": 68.8,
          "L95": 66.8
        },
        {
          "timestamp": 1746137467515,
          "Lv": 72.1,
          "Lvmax": 74.5,
          "Lvmin": 65.7,
          "L5": 74.3,
          "L10": 73.9,
          "L50": 71.5,
          "L90": 69.2,
          "L95": 68.5
        },
        {
          "timestamp": 1746137468517,
          "Lv": 72.9,
          "Lvmax": 74.5,
          "Lvmin": 65.7,
          "L5": 74.2,
          "L10": 73.9,
          "L50": 71.5,
          "L90": 69.2,
          "L95": 68.5
        },
        {
          "timestamp": 1746137469518,
          "Lv": 72.1,
          "Lvmax": 74.5,
          "Lvmin": 65.7,
          "L5": 74.2,
          "L10": 73.6,
          "L50": 71.5,
          "L90": 69.2,
          "L95": 68.5
        },
        {
          "timestamp": 1746137470520,
          "Lv": 67.5,
          "Lvmax": 74.5,
          "Lvmin": 65.7,
          "L5": 73.9,
          "L10": 73.4,
          "L50": 71.3,
          "L90": 68.8,
          "L95": 68.5
        },
        {
          "timestamp": 1746137471522,
          "Lv": 61.9,
          "Lvmax": 74.5,
          "Lvmin": 62.6,
          "L5": 73.9,
          "L10": 73.2,
          "L50": 70.9,
          "L90": 66.2,
          "L95": 65.0
        },
        {
          "timestamp": 1746137472522,
          "Lv": 55.4,
          "Lvmax": 74.5,
          "Lvmin": 56.0,
          "L5": 73.9,
          "L10": 73.0,
          "L50": 70.5,
          "L90": 61.9,
          "L95": 58.6
        },
        {
          "timestamp": 1746137473524,
          "Lv": 49.0,
          "Lvmax": 74.5,
          "Lvmin": 49.6,
          "L5": 73.9,
          "L10": 72.9,
          "L50": 70.0,
          "L90": 56.0,
          "L95": 52.8
        }
      ]
    }

*JOSN Object Items*
^^^^^^^^^^^^^^^^^^^

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
      - array<string>
      - データに関する補足情報　現在は計器のメーカーとモデル名が格納される
        
        Stores auxiliary information about this data, currently vendor and model names of the target measure.
    * - data_chunk
      - array<json-object>
      - :ref:`最小計測単位 <section-measureparameters-vibration>` の収集計測データが格納される配列
        
        Array stores the collected measurement data in the :ref:`minimum measurement unit <section-measureparameters-vibration>`.
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
  | Vibration measure built-in unit

*Destination IoT Topic*
^^^^^^^^^^^^^^^^^^^^^^^

aws/questar/soshinki/vibration/data_chunk

*Example*
^^^^^^^^^

.. code-block:: json

    {
      "device_id": "SK000010",
      "device_data_type": "vibration4/chunk",
      "data_version": "20250502",
      "data_no": 1,
      "data_key": "as",
      "data_aux": [
        "ACO TYPE3666"
      ],
      "data_chunk": [
        {
          "timestamp": 1746136836370,
          "Lv": 26.9
        },
        {
          "timestamp": 1746136837378,
          "Lv": 27.3
        },
        {
          "timestamp": 1746136838385,
          "Lv": 26.1
        },
        {
          "timestamp": 1746136839330,
          "Lv": 27.3
        },
        {
          "timestamp": 1746136840338,
          "Lv": 26.4
        },
        {
          "timestamp": 1746136841346,
          "Lv": 26.7
        },
        {
          "timestamp": 1746136842354,
          "Lv": 26.0
        },
        {
          "timestamp": 1746136843362,
          "Lv": 26.3
        },
        {
          "timestamp": 1746136844370,
          "Lv": 26.2
        },
        {
          "timestamp": 1746136845377,
          "Lv": 26.4
        },
        {
          "timestamp": 1746136846385,
          "Lv": 26.6
        },
        {
          "timestamp": 1746136847329,
          "Lv": 26.5
        }
      ]
    }

*JOSN Object Items*
^^^^^^^^^^^^^^^^^^^

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
      - array<string>
      - データに関する補足情報　現在は計器のメーカーとモデル名が格納される
        
        Stores auxiliary information about this data, currently vendor and model names of the target measure.
    * - data_chunk
      - array<json-object>
      - :ref:`最小計測単位 <section-measureparameters-vibration>` の収集計測データが格納される配列
        
        Array stores the collected measurement data in the :ref:`minimum measurement unit <section-measureparameters-vibration>`.
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
      "data_version": "20250502",
      "data_no": 1,
      "data_key": "wh",
      "data_aux": [
        "misol Weather Station WH24C"
      ],
      "data_chunk": [
        {
          "timestamp": 1746136973350,
          "wind_speed": 0.0,
          "gust_speed": 0.0,
          "wind_direction": 254,
          "temperature": 18.4,
          "humidity": 49,
          "accumulation_rainfall": 18.9,
          "uv": 0,
          "light": 0
        },
        {
          "timestamp": 1746136989349,
          "wind_speed": 0.0,
          "gust_speed": 0.0,
          "wind_direction": 254,
          "temperature": 18.4,
          "humidity": 49,
          "accumulation_rainfall": 18.9,
          "uv": 0,
          "light": 0
        },
        {
          "timestamp": 1746137005349,
          "wind_speed": 0.0,
          "gust_speed": 0.0,
          "wind_direction": 254,
          "temperature": 18.4,
          "humidity": 49,
          "accumulation_rainfall": 18.9,
          "uv": 0,
          "light": 0
        },
        {
          "timestamp": 1746137021350,
          "wind_speed": 0.0,
          "gust_speed": 0.0,
          "wind_direction": 254,
          "temperature": 18.4,
          "humidity": 49,
          "accumulation_rainfall": 18.9,
          "uv": 0,
          "light": 0
        }
      ]
    }

*JOSN Object Items*
^^^^^^^^^^^^^^^^^^^

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
      - array<string>
      - データに関する補足情報　現在は計器のメーカーとモデル名が格納される
        
        Stores auxiliary information about this data, currently vendor and model names of the target measure.
    * - data_chunk
      - array<json-object>
      - :ref:`最小計測単位 <section-measureparameters-weather>` の収集計測データが格納される配列
        
        Array stores the collected measurement data in the :ref:`minimum measurement unit <section-measureparameters-weather>`.
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
      "data_version": "20250502",
      "data_no": 1,
      "data_key": "dod",
      "data_aux": [
        "RION NL-42A"
      ],
      "data_sum": {
        "timestamp": 1746137282940,
        "noise_latest": 73.9,
        "noise_average": 65.3,
        "noise_l5": 76.0,
        "noise_l10": 74.45,
        "noise_l50": 66.3,
        "noise_l90": 60.0,
        "noise_l95": 52.35,
        "noise_max": 74.1,
        "noise_max_time": 1746137281939,
        "noise_min": 45.0,
        "noise_min_time": 1746137276932
      }
    }

*JOSN Object Items*
^^^^^^^^^^^^^^^^^^^

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
      - array<string>
      - データに関する補足情報　現在は計器のメーカーとモデル名が格納される
        
        Stores auxiliary information about this data, currently vendor and model names of the target measure.
    * - data_sum
      - json-object
      - :ref:`最小集計単位 <section-measureparameters-noise>` の計測データが格納される
        
        Stores measurement data in the :ref:`minimum aggregate unit <section-measureparameters-noise>`.
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
        
        Average noise value within the minimum aggregate unit time
    * - noise_l5
      - number
      - 最小集計単位時間内での騒音L5値
        
        L5 noise value within the minimum aggregate unit time
    * - noise_l10
      - number
      - 最小集計単位時間内での騒音L10値
        
        L10 noise value within the minimum aggregate unit time
    * - noise_l50
      - number
      - 最小集計単位時間内での騒音L50値
        
        L50 noise value within the minimum aggregate unit time
    * - noise_l90
      - number
      - 最小集計単位時間内での騒音L90値
        
        L90 noise value within the minimum aggregate unit time
    * - noise_l95
      - number
      - 最小集計単位時間内での騒音L95値
        
        L95 noise value within the minimum aggregate unit time
    * - noise_max
      - number
      - 最小集計単位時間内での騒音最大値
        
        Maximum noise value within the minimum aggregate unit time
    * - noise_max_time
      - number
      - noise_max 値の取得時刻　ミリ秒単位UNIX時刻 (UTC)
        
        Time at which the noise_max value was acquired. UNIX time in milliseconds (UTC)
    * - noise_min
      - number
      - 最小集計単位時間内での騒音最小値
        
        Minimum noise value within the minimum aggregate unit time
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
      "data_version": "20250502",
      "data_no": 1,
      "data_key": "dod",
      "data_aux": [
        "RION NL-43"
      ],
      "data_sum": {
        "timestamp": 1746139323314,
        "noise_latest": 75.2,
        "noise_average": 75.0,
        "noise_l5": 80.1,
        "noise_l10": 78.5,
        "noise_l50": 75.25,
        "noise_l90": 70.65,
        "noise_l95": 69.8,
        "noise_max": 78.6,
        "noise_max_time": 1746139316302,
        "noise_min": 70.5,
        "noise_min_time": 1746139314297
      }
    }

*JOSN Object Items*
^^^^^^^^^^^^^^^^^^^

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
      - array<string>
      - データに関する補足情報　現在は計器のメーカーとモデル名が格納される
        
        Stores auxiliary information about this data, currently vendor and model names of the target measure.
    * - data_sum
      - json-object
      - :ref:`最小集計単位 <section-measureparameters-noise>` の計測データが格納される
        
        Stores measurement data in the :ref:`minimum aggregate unit <section-measureparameters-noise>`.
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
        
        Average noise value within the minimum aggregate unit time
    * - noise_l5
      - number
      - 最小集計単位時間内での騒音L5値
        
        L5 noise value within the minimum aggregate unit time
    * - noise_l10
      - number
      - 最小集計単位時間内での騒音L10値
        
        L10 noise value within the minimum aggregate unit time
    * - noise_l50
      - number
      - 最小集計単位時間内での騒音L50値
        
        L50 noise value within the minimum aggregate unit time
    * - noise_l90
      - number
      - 最小集計単位時間内での騒音L90値
        
        L90 noise value within the minimum aggregate unit time
    * - noise_l95
      - number
      - 最小集計単位時間内での騒音L95値
        
        L95 noise value within the minimum aggregate unit time
    * - noise_max
      - number
      - 最小集計単位時間内での騒音最大値
        
        Maximum noise value within the minimum aggregate unit time
    * - noise_max_time
      - number
      - noise_max 値の取得時刻　ミリ秒単位UNIX時刻 (UTC)
        
        Time at which the noise_max value was acquired. UNIX time in milliseconds (UTC)
    * - noise_min
      - number
      - 最小集計単位時間内での騒音最小値
        
        Minimum noise value within the minimum aggregate unit time
    * - noise_max_time
      - number
      - noise_min 値の取得時刻　ミリ秒単位UNIX時刻 (UTC)
        
        Time at which the noise_min value was acquired. UNIX time in milliseconds (UTC)

.. note ::

    | `noise2/data_sum`_ は `noise1/data_sum`_ と同一形式
    | `noise2/data_sum`_ has same format as `noise1/data_sum`_.

noise4/data_sum
===============

*Target Measures*
^^^^^^^^^^^^^^^^^

- | アコー [ACO] TYPE3666 内蔵騒音計
  | Noise measure built-in unit

*Destination IoT Topic*
^^^^^^^^^^^^^^^^^^^^^^^

aws/questar/soshinki/noise/data_sum

*Example*
^^^^^^^^^

.. code-block:: json

    {
      "device_id": "SK000010",
      "device_data_type": "noise4/sum",
      "data_version": "20250502",
      "data_no": 1,
      "data_key": "as",
      "data_aux": [
        "ACO TYPE3666"
      ],
      "data_sum": {
        "timestamp": 1746137959264,
        "noise_latest": 61.0,
        "noise_average": 58.5,
        "noise_l5": 66.7,
        "noise_l10": 62.8,
        "noise_l50": 60.15,
        "noise_l90": 53.0,
        "noise_l95": 50.6,
        "noise_max": 67.6,
        "noise_max_time": 1746137951280,
        "noise_min": 46.1,
        "noise_min_time": 1746137956278
      }
    }

*JOSN Object Items*
^^^^^^^^^^^^^^^^^^^

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
      - array<string>
      - データに関する補足情報　現在は計器のメーカーとモデル名が格納される
        
        Stores auxiliary information about this data, currently vendor and model names of the target measure.
    * - data_sum
      - json-object
      - :ref:`最小集計単位 <section-measureparameters-noise>` の計測データが格納される
        
        Stores measurement data in the :ref:`minimum aggregate unit <section-measureparameters-noise>`.
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
        
        L5 noise value within the minimum aggregate unit time
    * - noise_l10
      - number
      - 最小集計単位時間内での騒音L10値
        
        L10 noise value within the minimum aggregate unit time
    * - noise_l50
      - number
      - 最小集計単位時間内での騒音L50値
        
        L50 noise value within the minimum aggregate unit time
    * - noise_l90
      - number
      - 最小集計単位時間内での騒音L90値
        
        L90 noise value within the minimum aggregate unit time
    * - noise_l95
      - number
      - 最小集計単位時間内での騒音L95値
        
        L95 noise value within the minimum aggregate unit time
    * - noise_max
      - number
      - 最小集計単位時間内での騒音最大値
        
        Maximum noise value within the minimum aggregate unit time
    * - noise_max_time
      - number
      - noise_max 値の取得時刻　ミリ秒単位UNIX時刻 (UTC)
        
        Time at which the vibration_max value was acquired. UNIX time in milliseconds (UTC)
    * - noise_min
      - number
      - 最小集計単位時間内での騒音最小値
        
        Minimum noise value within the minimum aggregate unit time
    * - noise_max_time
      - number
      - noise_min 値の取得時刻　ミリ秒単位UNIX時刻 (UTC)
        
        Time at which the vibration_min value was acquired. UNIX time in milliseconds (UTC)

.. note ::

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
      "data_version": "20250502",
      "data_no": 1,
      "data_key": "dod",
      "data_aux": [
        "RION VM-55"
      ],
      "data_sum": {
        "timestamp": 1746137473524,
        "vibration_latest": 49.0,
        "vibration_average": 66.3,
        "vibration_l5": 73.9,
        "vibration_l10": 73.5,
        "vibration_l50": 71.2,
        "vibration_l90": 68.65,
        "vibration_l95": 66.8,
        "vibration_max": 74.3,
        "vibration_max_time": 1746137466514,
        "vibration_min": 49.0,
        "vibration_min_time": 1746137473524
      }
    }

*JOSN Object Items*
^^^^^^^^^^^^^^^^^^^

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
      - array<string>
      - データに関する補足情報　現在は計器のメーカーとモデル名が格納される
        
        Stores auxiliary information about this data, currently vendor and model names of the target measure.
    * - data_sum
      - json-object
      - :ref:`最小集計単位 <section-measureparameters-vibration>` の計測データが格納される
        
        Stores measurement data in the :ref:`minimum aggregate unit <section-measureparameters-vibration>`.
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
        
        Average vibration value within the minimum aggregate unit time
    * - vibration_l5
      - number
      - 最小集計単位時間内での振動L5値
        
        L5 vibration value within the minimum aggregate unit time
    * - vibration_l10
      - number
      - 最小集計単位時間内での振動L10値
        
        L10 vibration value within the minimum aggregate unit time
    * - vibration_l50
      - number
      - 最小集計単位時間内での振動L50値
        
        L50 vibration value within the minimum aggregate unit time
    * - vibration_l90
      - number
      - 最小集計単位時間内での振動L90値
        
        L90 vibration value within the minimum aggregate unit time
    * - vibration_l95
      - number
      - 最小集計単位時間内での振動L95値
        
        L95 vibration value within the minimum aggregate unit time
    * - vibration_max
      - number
      - 最小集計単位時間内での振動最大値
        
        Maximum vibration value within the minimum aggregate unit time
    * - vibration_max_time
      - number
      - vibration_max 値の取得時刻　ミリ秒単位UNIX時刻 (UTC)
        
        Time at which the vibration_max value was acquired. UNIX time in milliseconds (UTC)
    * - vibration_min
      - number
      - 最小集計単位時間内での振動最小値
        
        Minimum vibration value within the minimum aggregate unit time
    * - vibration_min_time
      - number
      - vibration_min 値の取得時刻　ミリ秒単位UNIX時刻 (UTC)
        
        Time at which the vibration_min value was acquired. UNIX time in milliseconds (UTC)

vibration4/data_sum
===================

*Target Measures*
^^^^^^^^^^^^^^^^^

- | アコー [ACO] TYPE3666 内蔵振動計
  | Vibration measure built-in unit

*Destination IoT Topic*
^^^^^^^^^^^^^^^^^^^^^^^

aws/questar/soshinki/vibration/data_sum

*Example*
^^^^^^^^^

.. code-block:: json

    {
      "device_id": "SK000010",
      "device_data_type": "vibration4/sum",
      "data_version": "20250502",
      "data_no": 1,
      "data_key": "as",
      "data_aux": [
        "ACO TYPE3666"
      ],
      "data_sum": {
        "timestamp": 1746136847329,
        "vibration_latest": 26.5,
        "vibration_average": 26.6,
        "vibration_l5": 27.3,
        "vibration_l10": 26.9,
        "vibration_l50": 26.45,
        "vibration_l90": 26.2,
        "vibration_l95": 26.1,
        "vibration_max": 27.3,
        "vibration_max_time": 1746136837378,
        "vibration_min": 26.0,
        "vibration_min_time": 1746136842354
      }
    }

*JOSN Object Items*
^^^^^^^^^^^^^^^^^^^

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
      - array<string>
      - データに関する補足情報　現在は計器のメーカーとモデル名が格納される
        
        Stores auxiliary information about this data, currently vendor and model names of the target measure.
    * - data_sum
      - json-object
      - :ref:`最小集計単位 <section-measureparameters-vibration>` の計測データが格納される
        
        Stores measurement data in the :ref:`minimum aggregate unit <section-measureparameters-vibration>`.
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
        
        Average vibration value within the minimum aggregate unit time
    * - vibration_l5
      - number
      - 最小集計単位時間内での振動L5値
        
        L5 vibration value within the minimum aggregate unit time
    * - vibration_l10
      - number
      - 最小集計単位時間内での振動L10値
        
        L10 vibration value within the minimum aggregate unit time
    * - vibration_l50
      - number
      - 最小集計単位時間内での振動L50値
        
        L50 vibration value within the minimum aggregate unit time
    * - vibration_l90
      - number
      - 最小集計単位時間内での振動L90値
        
        L90 vibration value within the minimum aggregate unit time
    * - vibration_l95
      - number
      - 最小集計単位時間内での振動L95値
        
        L95 vibration value within the minimum aggregate unit time
    * - vibration_max
      - number
      - 最小集計単位時間内での振動最大値
        
        Maximum vibration value within the minimum aggregate unit time
    * - vibration_max_time
      - number
      - vibration_max 値の取得時刻　ミリ秒単位UNIX時刻 (UTC)
        
        Time at which the vibration_max value was acquired. UNIX time in milliseconds (UTC)
    * - vibration_min
      - number
      - 最小集計単位時間内での振動最小値
        
        Minimum vibration value within the minimum aggregate unit time
    * - vibration_min_time
      - number
      - vibration_min 値の取得時刻　ミリ秒単位UNIX時刻 (UTC)
        
        Time at which the vibration_min value was acquired. UNIX time in milliseconds (UTC)

.. note ::

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
      "data_version": "20250502",
      "data_no": 1,
      "data_key": "wh",
      "data_aux": [
        "misol Weather Station WH24C"
      ],
      "data_sum": {
        "timestamp": 1746137021350,
        "wind_speed_latest": 0.0,
        "wind_speed_average": 0.0,
        "wind_speed_l50": 0.0,
        "wind_speed_max": 0.0,
        "wind_speed_max_time": 1746136973350,
        "wind_speed_min": 0.0,
        "wind_speed_min_time": 1746136973350,
        "gust_speed_latest": 0.0,
        "gust_speed_l50": 0.0,
        "wind_direction_latest": 254,
        "wind_direction_l50": 254,
        "temperature_latest": 18.4,
        "temperature_l50": 18.4,
        "humidity_latest": 49,
        "humidity_l50": 49,
        "accumulation_rainfall_latest": 18.9,
        "accumulation_rainfall_l50": 18.9,
        "uv_latest": 0,
        "uv_l50": 0,
        "light_latest": 0,
        "light_l50": 0
      }
    }

*JOSN Object Items*
^^^^^^^^^^^^^^^^^^^

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
      - array<string>
      - データに関する補足情報　現在は計器のメーカーとモデル名が格納される
        
        Stores auxiliary information about this data, currently vendor and model names of the target measure.
    * - data_sum
      - json-object
      - :ref:`最小集計単位 <section-measureparameters-weather>` の計測データが格納される
        
        Stores measurement data in the :ref:`minimum aggregate unit <section-measureparameters-weather>`.
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
        
        Average wind speed value within the minimum aggregate unit time
    * - wind_speed_l50
      - number
      - 最小集計単位時間内での風速L50値
        
        L50 wind speed value within the minimum aggregate unit time
    * - wind_speed_max
      - number
      - 最小集計単位時間内での風速最大値
        
        Maximum wind speed value within the minimum aggregate unit time
    * - wind_speed_max_time
      - number
      - wind_speed_max 値の取得時刻　ミリ秒単位UNIX時刻 (UTC)
        
        Time at which the wind_speed_max value was acquired. UNIX time in milliseconds (UTC)
    * - wind_speed_min
      - number
      - 最小集計単位時間内での風速最小値
        
        Minimum wind speed value within the minimum aggregate unit time
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
        
        L50 wind gust speed value within the minimum aggregate unit time
    * - wind_direction_latest
      - number
      - 計測データ取得時の風向最新値
        
        Latest wind direction value at this data was acquired
    * - wind_direction_l50
      - number
      - 最小集計単位時間内での風向L50値
        
        L50 wind direction value within the minimum aggregate unit time
    * - temperature_latest
      - number
      - 計測データ取得時の温度最新値
        
        Latest temperature value at this data was acquired
    * - temperature_l50
      - number
      - 最小集計単位時間内での温度L50値
        
        L50 temperature value within the minimum aggregate unit time
    * - humidity_latest
      - number
      - 計測データ取得時の湿度最新値
        
        Latest humidity value at this data was acquired
    * - humidity_l50
      - number
      - 最小集計単位時間内での湿度L50値
        
        L50 humidity value within the minimum aggregate unit time
    * - accumulation_rainfall_latest
      - number
      - 計測データ取得時の積算雨量最新値
        
        Latest accumulation rainfall value at this data was acquired
    * - accumulation_rainfall_l50
      - number
      - 最小集計単位時間内での積算雨量L50値
        
        L50 accumulation rainfall value within the minimum aggregate unit time
    * - uv_latest
      - number
      - 計測データ取得時の紫外線量最新値
        
        Latest UV index value at this data was acquired
    * - uv_l50
      - number
      - 最小集計単位時間内での紫外線量L50値
        
        L50 UV index value within the minimum aggregate unit time
    * - light_latest
      - number
      - 計測データ取得時の光照度最新値
        
        Latest light illuminance value at this data was acquired
    * - light_l50
      - number
      - 最小集計単位時間内での光照度L50値
        
        L50 light illuminance value within the minimum aggregate unit time

.. note ::

    | L50は最小集計時間内での中央値を表しています
    | L50 means median value within the minimum aggregate unit time.

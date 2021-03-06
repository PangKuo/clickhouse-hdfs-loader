# clickhouse-hdfs-loader
loading hdfs data to clickhouse，Support text or orc.
## Options
       --batch-size N                : batch size load data into clickhouse (default:
                                       100000)
       --clickhouse-format VAL       : 导入到Clickhouse的数据格式，一般保留默认配置。支持[TabSeparated|Tab
                                       SeparatedWithNames|TabSeparatedWithNamesAndType
                                       s|TabSeparatedRaw|CSV|CSVWithNames] (default:
                                       TabSeparated)
       --connect VAL                 : jdbc:clickhouse://<host>:<port>/<database>
       --daily VAL                   : 是否把每天的数据导入到独立的日表 (default: false)
       --daily-expires N             : 导入时将会判断过期日表，默认保留3天的日表数据 (default: 3)
       --daily-expires-process VAL   : 过期日表的处理规则：merge:把过期日表数据导入base表后删除日表，drop:把过期日表删
                                       除 (default: merge)
       --driver VAL                  : 驱动类名，一般保留默认配置 (default: ru.yandex.clickhouse.Cl
                                       ickHouseDriver)
       --dt VAL                      : 导入数据的业务时间,format:YYYY-MM-DD
       --exclude-fields VAL          : 数据源每行数据，被排除的字段下标，从0开始
       --export-dir VAL              : 数据源HDFS路径
       --extract-hive-partitions VAL : 是否根据数据源路径抽取hive分区，如xxx/dt=2017-01-01/pt=ios，将会抽
                                       取出两个分区字段，并按顺序追加到每行数据后面。 (default: false)
       --fields-terminated-by VAL    : 数据源文件字段分隔符 (default: |)
       --input-format VAL            : Deprecated!请使用-i参数替代.  (default:
                                       org.apache.orc.mapreduce.OrcInputFormat)
       --mapper-class VAL            : Deprecated!请使用-i参数替代.  (default:
                                       com.kugou.loader.clickhouse.mapper.OrcLoaderMap
                                       per)
       --max-tries N                 : 当在导入发生异常时的重试次数 (default: 3)
       --mode VAL                    : <append> 导入时如果日表已存在，数据将会追加到该日表.
                                       <drop> 导入时如果日表已存在，将会删除后，重建日表. (default: append)
       --num-reduce-tasks N          : 指定reduce task的个数，一般保留默认配置 (default: -1)
       --replace-char VAL            : 替换在字段内容中存在的分隔符关键字，如clickhouse-format=CSV时，分隔符关键
                                       字为','，字段内容中存在将会被替换 (default:  )
       --table VAL                   : 导入目标表名
       -i VAL                        : 数据源文件存储格式，支持[text|orc]


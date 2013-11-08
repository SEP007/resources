# Suitability of Patat

## Measurement collection

The  Functional Implementation Coverage metric is used to measure the suitability of Patat.  The metrics take into account the number of incorrectly implemented or missing  stories and the number of stories listed in the product backlog.  Stories can be both, user and developer stories. The number of incorrectly implemented or missing stories are  measured at the end of each sprint, when functional tests are conducted, because it is then that the team decides mutually whether a story is accepted or has to be reassigned because of an incomplete or incorrect implementation. The number of stories listed in the product backlog can vary from one sprint to the next because the team might decide to split up complex stories into multiple stories or add completely new stories to the product backlog.  Hence, if the number of incorrectly implemented or missing stories is compared to the number of stories in the product backlog at the end of each sprint, it is possible that the Functional Implementation Coverage decreases from one sprint to the next, even if stories have been accepted since the last sprint. So, the number of incorrectly implemented or missing stories is compared to the number of stories that were in the initial product backlog.  
The outcome of each measurement and comparison is documented at the end of a sprint and visualized in the shape of two burndown charts. Since Huboard, the tool that has been picked to track stories, does not produce a burndown chart automatically, data has to be collected and treated manually. Apart from enabling the team to monitor Patat’s suitability, the burndown charts can be used as mean to keep track of the team’s performance and as decision support. 

## Measurement results

| 				    | Project start   | End of 1st sprint |
| :---------------: | :-------------: | ----------------: |
| Accepted          | 0               | 4                 |
| Not accepted      | 0               | 2                 |
| Not started       | 24              | 19                |
| In total          | 24              | 25                |
| Measured at       | 01.11.2013      | 07.11.2013        |

## Burndown chart

![alt text](https://raw.github.com/SEP007/resources/master/quality-metrics/suitability/resources/burndown_chart1.png)

## Burndown chart (relative to project start)

![alt text](https://raw.github.com/SEP007/resources/master/quality-metrics/suitability/resources/burndown_chart2.png)

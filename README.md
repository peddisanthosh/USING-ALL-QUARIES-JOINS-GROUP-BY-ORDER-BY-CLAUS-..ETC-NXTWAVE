SELECT
  video.channel_id,
  channel.name AS channel_name
FROM
  video
  INNER JOIN channel ON video.channel_id = channel.channel_id
WHERE
  video.name LIKE "%music%"
  AND strftime("%Y", published_datetime) < "2016"
GROUP BY
  channel_name
ORDER BY
  channel_name ASC;


---
type: daily_record
date: <% tp.file.title.match(/^\d{4}-\d{2}-\d{2}$/) ? tp.file.title : tp.date.now("YYYY-MM-DD") %>
tags:
  - daily_record
---

# 日记

<%*
const recordDate = tp.file.title.match(/^\d{4}-\d{2}-\d{2}$/)
  ? moment(tp.file.title, "YYYY-MM-DD")
  : moment(tp.date.now("YYYY-MM-DD"), "YYYY-MM-DD");

function durationSince(startDate, endDate) {
  const cursor = startDate.clone();
  const years = endDate.diff(cursor, "years");
  cursor.add(years, "years");
  const months = endDate.diff(cursor, "months");
  cursor.add(months, "months");
  const days = endDate.diff(cursor, "days");
  const totalDays = endDate.diff(startDate, "days") + 1;

  return { years, months, days, totalDays };
}

function formatDuration(duration) {
  const parts = [`${duration.years} 年`, `${duration.months} 个月`];
  if (duration.days > 0) {
    parts.push(`${duration.days} 天`);
  }

  return parts.join(" ");
}

const weekdays = ["星期日", "星期一", "星期二", "星期三", "星期四", "星期五", "星期六"];
const bytedanceTenure = durationSince(moment("2020-04-08", "YYYY-MM-DD"), recordDate);
const beijingTenure = durationSince(moment("2017-12-22", "YYYY-MM-DD"), recordDate);
const relationshipTenure = durationSince(moment("2018-03-15", "YYYY-MM-DD"), recordDate);

tR += `> 今天是 ${recordDate.format("YYYY-MM-DD")}，${weekdays[recordDate.day()]}。\n`;
tR += `> 今天是和🥚💗在一起的第 ${relationshipTenure.totalDays} 天，已经 ${formatDuration(relationshipTenure)}。\n`;
tR += `> 今天是入职字节的第 ${bytedanceTenure.totalDays} 天，已经 ${formatDuration(bytedanceTenure)}。\n`;
tR += `> 今天是来到北京的第 ${beijingTenure.totalDays} 天，已经 ${formatDuration(beijingTenure)}。`;
%>

## 一句话总结

-

## 今天做了什么

### 工作

-

### 生活

-

## 今天学到了什么

-

## 今天的想法

-

## 明天要做什么

- [ ] 最重要：
- [ ]

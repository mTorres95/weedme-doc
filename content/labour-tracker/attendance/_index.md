+++
title = "Attendance"
weight = 400
+++

## Attendance

The app also replace the old punch-in and punch-out card system. Since, it
register when a worker arrives to the facility and when it leaves it.

## Worker's ID

Once a worker is created it, the app generate a QR Image to be used on the
Worker's ID. This QR Code can be downloaded by an Human Resources user and
download to setup a Worker ID.

## Facility User

There is a computer at the entrance and exit of the facility logged in to the
app with the **Facility User**. The browser needs to be on full screen and
focused on the main view.

### QR Scanner

An 2D scanner needs to be hook up to the facility computer. It listen all the
time for new QR Codes (Worker IDs).

When a worker scan the Worker ID on the scanner, the view will return a friendly message showing if the worker clocks in or clocks out from the facility.

## Report

A Human Resources user can review or download individual clock in and clock out
csv report for each worker.
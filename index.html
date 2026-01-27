<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Schedule Me Scheduler</title>
    <style>
        :root {
            --primary: #BE2227;
            --primary-dark: #901a1e;
            --bg: #f3f4f6;
            --surface: #ffffff;
            --border: #d1d5db;
            --text-main: #1f2937;
            --text-muted: #6b7280;
            --danger: #dc2626; 
            --success: #059669;
            --warning: #d97706;
        }

        body { font-family: 'Segoe UI', system-ui, sans-serif; background: var(--bg); margin: 0; padding: 20px; color: var(--text-main); }
        h1, h3 { color: var(--text-main); margin-top: 0; }

        .header { display: flex; justify-content: space-between; align-items: center; margin-bottom: 20px; }
        .header-controls { display: flex; gap: 10px; align-items: center; }
        
        .main-layout { display: grid; grid-template-columns: 240px 280px 1fr; gap: 20px; }
        .sidebar-col { position: relative; display: flex; flex-direction: column; gap: 20px; }

/* STICKY SIDEBAR LAYOUT */
        .sticky-wrapper {
            position: sticky;        /* KEY: Follows you as you scroll */
            top: 20px;               /* Stays 20px from the top */
            z-index: 50;
            
            /* Fit to screen height (Viewport - Top Margin - Bottom Margin) */
            height: calc(100vh - 40px); 
            
            /* Flex layout to split space between panels */
            display: flex;
            flex-direction: column;
            gap: 15px;
            overflow: visible;        /* Prevents the wrapper itself from scrolling */
        }

        /* Make Panels flexible containers */
        .sidebar-col .panel {
            flex: 1;                 /* Each panel takes equal available space */
            display: flex;           /* Flex column for internal alignment */
            flex-direction: column;
            min-height: 0;           /* Critical for nested scrolling */
            margin-bottom: 0;        /* Let gap handle spacing */
            padding-bottom: 10px;    /* Slight padding at bottom of panel */
        }

        /* Make the lists inside scrollable */
        .staff-pool-list, .favorites-list, #job-list { 
            flex: 1;                 /* Fill the remaining panel space */
            min-height: 0;           /* Allow shrinking inside flex panels */
            overflow-y: auto;        /* Scroll ONLY the list */
            margin-bottom: 0;
            margin-top: 10px;

            /* Visual styling (moved from the old fixed-height rule) */
            padding: 8px; 
            background: #f8fafc; 
            border: 1px solid var(--border); 
            border-radius: 6px; 
        }

        .panel { background: var(--surface); padding: 20px; border-radius: 8px; box-shadow: 0 4px 6px -1px rgba(0,0,0,0.1); border: 1px solid var(--border); }

        /* DAILY NOTES */
        .btn-edit-note { 
            border: none; background: none; cursor: pointer; color: var(--text-muted); 
            font-size: 0.9rem; padding: 0 4px; transition: color 0.2s; 
        }
        .btn-edit-note:hover { color: var(--primary); }
        .day-note { 
            display: block; font-size: 0.75rem; color: var(--danger); 
            font-weight: 700; margin-top: 4px; white-space: normal; line-height: 1.2;
        }
        
        /* TOGGLE & BUTTONS */
        .view-toggle { display: flex; border-radius: 6px; overflow: hidden; border: 1px solid var(--primary); }
        .view-toggle button { padding: 8px 16px; cursor: pointer; border: none; background: var(--surface); color: var(--primary); font-weight: 600; margin: 0; border-right: 1px solid var(--primary); transition: all 0.2s; }
        .view-toggle button:last-child { border-right: none; }
        .view-toggle button.active { background: var(--primary); color: white; }

        button { cursor: pointer; font-weight: 600; transition: background 0.2s; }
        button.primary { background: var(--primary); color: white; border: 1px solid var(--primary); margin-top: 10px; }
        button.primary:hover { background: var(--primary-dark); }
        button.action-btn { background: #374151; color: white; border: none; margin-bottom: 8px; width: 100%; padding: 8px; border-radius: 4px; }
        button.danger-btn { background: #fee2e2; color: #991b1b; border: 1px solid #f87171; margin-top: 10px; width: 100%; padding: 8px; border-radius: 4px; }

        /* INPUTS - FIXED SPACING */
        .control-group { margin-bottom: 15px; }
        label { display: block; font-size: 0.85rem; font-weight: 700; margin-bottom: 5px; color: var(--text-muted); }
        select, input { width: 100%; padding: 8px; margin-bottom: 5px; border: 1px solid var(--border); border-radius: 4px; box-sizing: border-box; background: var(--surface); }
        
        /* Stack labels and inputs vertically for better readability */
        .time-row { margin-bottom: 10px; }
        .time-row label { margin-bottom: 4px; display: block; }
        .time-selects { display: flex; gap: 8px; }
        .time-selects select { flex: 1; }

/* PRETTY SCROLLBARS */
        .staff-pool-list::-webkit-scrollbar, 
        .favorites-list::-webkit-scrollbar, 
        #job-list::-webkit-scrollbar {
            width: 6px;
        }
        .staff-pool-list::-webkit-scrollbar-thumb, 
        .favorites-list::-webkit-scrollbar-thumb, 
        #job-list::-webkit-scrollbar-thumb {
            background-color: #cbd5e1;
            border-radius: 4px;
        }

        /* STAFF CARDS (Polished Look) */
        .draggable-emp { 
            display: flex;
            align-items: center;
            justify-content: space-between;
            background: white; 
            padding: 10px 12px;      /* More breathing room */
            margin-bottom: 6px; 
            border-radius: 6px; 
            border: 1px solid #e2e8f0; 
            cursor: grab; 
            font-weight: 600; 
            color: var(--text-main);
            box-shadow: 0 1px 2px rgba(0,0,0,0.04);
            transition: transform 0.1s, box-shadow 0.1s;
        }
        .draggable-emp:hover {
            transform: translateY(-1px);
            box-shadow: 0 3px 5px rgba(0,0,0,0.06);
            border-color: #cbd5e1;
        }
        .draggable-emp:active { cursor: grabbing; opacity: 0.8; }

        /* JOB PILLS (Polished Look) */
        .job-pill {
            display: flex;
            align-items: center;
            justify-content: space-between;
            background: #eef2ff; 
            border: 1px solid #c7d2fe; 
            color: #4338ca;
            padding: 10px 12px;      /* Consistent with staff cards */
            border-radius: 6px; 
            cursor: grab; 
            font-weight: 600;
            margin-bottom: 6px;
            font-size: 0.9rem;
            box-shadow: 0 1px 2px rgba(0,0,0,0.03);
        }
        .job-pill:active { cursor: grabbing; opacity: 0.8; }

        /* Drag Handle Icon Fix */
        .emp-content { 
            display: flex; 
            align-items: center; 
            gap: 10px; 
        }
        .emp-content::before { 
            content: '⋮⋮'; 
            color: #94a3b8; 
            font-size: 1.1em; 
            letter-spacing: -2px;
            cursor: grab;
        }
        
        /* Remove Button Fix */
        .btn-remove-staff { 
            color: #cbd5e1; 
            font-size: 1.2rem; 
            line-height: 1; 
            padding: 4px;
            border-radius: 4px;
            cursor: pointer;
            border: none;
            background: transparent;
        }
        .btn-remove-staff:hover { 
            color: var(--danger); 
            background: #fee2e2;
        }

/* Edit Staff Button */
        .btn-edit-staff { 
            color: #94a3b8; 
            font-size: 1rem; 
            padding: 4px;
            border-radius: 4px;
            cursor: pointer;
            border: none;
            background: transparent;
            margin-right: 4px;
        }
        .btn-edit-staff:hover { 
            color: var(--primary); 
            background: #fee2e2;
        }

        /* DRAGGABLE SHIFT SOURCE */
        .draggable-shift-source { background: var(--surface); color: var(--primary); padding: 15px; border-radius: 6px; cursor: grab; text-align: center; font-weight: bold; box-shadow: 0 4px 6px -1px rgba(0,0,0,0.1); border: 2px solid var(--primary); margin-bottom: 15px; }
        .source-icon { font-size: 1.2rem; display: block; margin-bottom: 5px; }

/* DATA MANAGEMENT TOP BAR */
        .schedule-column {
            display: flex;
            flex-direction: column;
            gap: 20px;
        }
        
        .data-management-bar {
            display: flex;
            gap: 10px;
            align-items: center;
            background: white;
            padding: 10px 15px;
            border: 1px solid var(--border);
            border-radius: 8px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.05);
        }
        
        .data-management-bar h3 {
            margin: 0;
            font-size: 1rem;
            margin-right: auto; /* Pushes buttons to the right */
            color: var(--text-muted);
            text-transform: uppercase;
            letter-spacing: 0.5px;
        }

        .data-management-bar button {
            width: auto; /* Reset full width */
            margin: 0;
            padding: 8px 16px;
            font-size: 0.85rem;
        }
        
        /* Specific button tweaks for the bar */
        .data-management-bar .action-btn { background: #4b5563; }
        .data-management-bar .action-btn:hover { background: #374151; }

/* NAVIGATION GROUP */
        .nav-group {
            display: flex;
            align-items: center;
            background: white;
            border: 1px solid var(--primary);
            border-radius: 6px;
            overflow: hidden;
        }
        .nav-group input {
            border: none;
            border-radius: 0;
            margin: 0;
            height: 36px;
            text-align: center;
        }
        .nav-group button {
            background: white;
            color: var(--primary);
            border: none;
            border-radius: 0;
            margin: 0;
            padding: 0 10px;
            font-size: 1.2rem;
            height: 36px;
            cursor: pointer;
        }
        .nav-group button:hover {
            background: #f3f4f6;
        }

/* FAVORITES */
        .favorites-drop-zone {
            border: 2px dashed #9ca3af; 
            background: #f9fafb; 
            color: #6b7280; 
            padding: 15px; 
            text-align: center; 
            border-radius: 6px; 
            margin-bottom: 15px; 
            font-size: 0.85rem; 
            transition: background 0.2s;
        }
        .favorites-drop-zone.drag-over { 
            background: #e5e7eb; 
            border-color: var(--primary); 
            color: var(--primary); 
        }
        
        .favorites-list { 
            display: flex; 
            flex-direction: column; 
            gap: 8px; 
        }
        
        .favorite-item {
            background: white; 
            border: 1px solid var(--border); 
            border-left: 4px solid var(--primary); 
            padding: 10px 12px; /* Increased padding */
            border-radius: 4px; 
            cursor: grab; 
            display: flex; 
            justify-content: space-between; 
            align-items: center; 
            font-size: 0.85rem; 
            font-weight: 600; 
            box-shadow: 0 1px 2px rgba(0,0,0,0.05);
        }
        .favorite-item:active { cursor: grabbing; }
        
        .fav-info { 
            display: flex; 
            flex-direction: column; 
        }
        
        /* THIS FIXES THE SQUISHING: Adds space below the time range */
        .fav-info span:first-child {
            margin-bottom: 4px;
            font-size: 0.9rem;
            color: var(--text-main);
        }

        .fav-sub { 
            font-size: 0.75rem; 
            color: var(--primary); 
            font-weight: bold; 
        }

        /* GRID & CARDS */
        .week-container { margin-bottom: 30px; background: white; border-radius: 8px; box-shadow: 0 1px 3px rgba(0,0,0,0.1); overflow: hidden; border: 1px solid var(--border); }
        table { width: 100%; border-collapse: collapse; table-layout: fixed; }
        th { background: #f9fafb; font-weight: 600; color: var(--text-muted); padding: 12px; border-bottom: 2px solid var(--border); text-align: left; font-size: 0.9rem; }
        td { padding: 10px; border-bottom: 1px solid var(--border); border-right: 1px solid #f3f4f6; vertical-align: top; height: 80px; transition: background 0.2s; }
        .col-emp { width: 180px; background: #fff; border-right: 2px solid var(--border); color: var(--text-main); }
        .col-time { width: 80px; background: #f9fafb; border-right: 2px solid var(--border); text-align: center; vertical-align: middle; font-weight: bold; color: var(--text-muted); }
        .drop-row td { height: 40px; background: #fff1f2; border-bottom: 2px dashed var(--primary); color: var(--primary); text-align: center; vertical-align: middle; font-weight: bold; font-size: 0.85rem; }
        .drop-row.drag-over td { background: #ffe4e6; }
        td.cell-drag-over { background: #fef2f2 !important; box-shadow: inset 0 0 0 2px var(--primary); }
        td.unavailable { background-color: #e5e7eb; background-image: repeating-linear-gradient(45deg, #d1d5db 0, #d1d5db 1px, transparent 0, transparent 50%); background-size: 10px 10px; }
        
        .shift-card { background: #ffffff; border: 1px solid var(--border); border-left: 4px solid var(--primary); padding: 8px 10px; margin-bottom: 6px; border-radius: 4px; font-size: 0.75rem; position: relative; box-shadow: 0 1px 3px rgba(0,0,0,0.05); cursor: grab; }
        .shift-time { font-weight: 500; display: block; color: var(--text-main); font-size: 0.85rem; margin-bottom: 4px; }
        .status-ok { background: #d1fae5; color: #065f46; border: 1px solid #a7f3d0; }
        .status-over { background: #fee2e2; color: #991b1b; border: 1px solid #fecaca; } 
        .status-under { background: #fef3c7; color: #92400e; border: 1px solid #fde68a; }
        .emp-hours { font-size: 0.75rem; font-weight: 700; padding: 2px 8px; border-radius: 99px; display: inline-block; margin-top: 4px; }
        .ot-tag { display: block; font-size: 0.7rem; color: var(--danger); font-weight: 800; }
.hour-chip { 
            display: inline-block; 
            background: white; 
            border: 1px solid var(--border); 
            border-left: 3px solid var(--primary); 
            padding: 2px 6px; 
            border-radius: 4px; 
            font-size: 0.75rem; 
            margin: 2px; 
            font-weight: 600; 
            cursor: pointer; /* Added pointer */
            transition: all 0.2s;
        }
        .hour-chip:hover {
            background-color: var(--bg);
            border-color: var(--primary-dark);
        }
        .emp-drag-handle { cursor: grab; font-weight: bold; display: flex; align-items: center; gap: 6px; }

/* Lunch Indicator for Hourly View */
        .hour-chip.on-lunch {
            background-color: #fff7ed; /* Light Orange */
            border-left: 3px solid #f97316; /* Orange */
            color: #c2410c;
            opacity: 0.8;
        }

/* Badge displayed on the Shift Card */
        .shift-job-badge {
            display: inline-block;
            background: #6366f1;
            color: white;
            font-size: 0.7rem;
            padding: 1px 5px;
            border-radius: 4px;
            margin-top: 3px;
            font-weight: normal;
        }

        /* MODAL */
        dialog { border: none; border-radius: 8px; box-shadow: 0 20px 25px -5px rgba(0,0,0,0.1); padding: 25px; width: 350px; background: var(--surface); }
        dialog::backdrop { background: rgba(0,0,0,0.5); }
        .day-checkboxes { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; margin-top: 5px; }
        .day-checkboxes label { font-weight: normal; cursor: pointer; display: flex; align-items: center; gap: 8px; font-size: 0.9rem; }
        .day-checkboxes input { width: auto; margin: 0; accent-color: var(--primary); }
        .dialog-buttons { display: flex; gap: 10px; margin-top: 20px; }
        .dialog-buttons button { flex: 1; margin: 0; height: 40px; }

        #message-box { padding: 10px; border-radius: 4px; font-size: 0.9rem; margin-top: 10px; display: none; }
        .msg-error { background: #fee2e2; color: #991b1b; border: 1px solid #f87171; }
        .msg-success { background: #dcfce7; color: #166534; border: 1px solid #4ade80; }

/* TASKS VIEW STYLES */
        .task-category-header {
            background-color: #1f2937; /* Dark Grey/Blue */
            color: white;
            font-weight: bold;
            text-transform: uppercase;
            padding: 8px 12px;
            text-align: left;
        }
        
        .task-name-cell {
            background: #f9fafb;
            font-weight: 600;
            font-size: 0.85rem;
            color: var(--text-main);
            width: 250px; /* Wider column for task names */
            border-right: 2px solid var(--border);
        }

        .task-assign-cell {
            height: 40px; /* Fixed height for consistency */
            vertical-align: middle;
            text-align: center;
            transition: background 0.2s;
        }
        .task-assign-cell.drag-over { background: #e0f2fe; }

        .task-chip {
            display: inline-flex;
            align-items: center;
            gap: 5px;
            background: white;
            border: 1px solid var(--primary);
            color: var(--primary);
            padding: 2px 8px;
            border-radius: 99px;
            font-size: 0.75rem;
            font-weight: bold;
            box-shadow: 0 1px 2px rgba(0,0,0,0.05);
        }


/* RESPONSIVE LAYOUT */
@media (max-width: 980px) {
    body { padding: 12px; }
    .header { flex-direction: column; align-items: flex-start; gap: 10px; }
    .header-controls { flex-wrap: wrap; width: 100%; }
    .main-layout { grid-template-columns: 1fr; gap: 15px; }
    .sticky-wrapper { position: static; height: auto; overflow: visible; }
    .sidebar-col .panel { flex: none; }
    .data-management-bar { flex-wrap: wrap; }
    .nav-group input { width: 160px; }
}

@media print {
    @page { 
        size: landscape; 
        margin: 0.5cm; 
    }
    
    body { 
        background: white; 
        padding: 0; 
        margin: 0; 
        zoom: 65%; 
        -webkit-print-color-adjust: exact; 
        width: 100%;
        max-width: 100%;
        overflow-x: hidden; 
    }
    
    /* Hide interface elements */
    .header-controls, 
    .tooltip-trigger,
    .sidebar-col, 
    .drop-row, 
    button, 
    #message-box, 
    .btn-delete, 
    .data-management-bar,
    .view-toggle,
    .nav-group { 
        display: none !important;
    } 

    /* Layout Adjustments */
    .main-layout { display: block; width: 100%; margin: 0; }
    #schedule-container { width: 100%; margin: 0; }
    
    .week-container { 
        border: none; 
        box-shadow: none; 
        margin-bottom: 10px; 
        page-break-inside: avoid; 
        width: 100%;
        overflow: visible !important;
    }
    
    /* COMPACT TABLE STYLES */
    table { width: 100%; table-layout: fixed; border-collapse: collapse; }
    
    th { 
        padding: 4px; 
        font-size: 10pt; 
        background: #f3f4f6 !important; 
        border: 1px solid #9ca3af; 
        color: #000; 
        height: 20px;
    }
    
    td { 
        height: auto !important; 
        padding: 2px !important; 
        border: 1px solid #9ca3af; 
        font-size: 9pt; 
        vertical-align: middle;
    }
    
    tr.empty-row { display: none !important; }
    .col-emp { width: 110px; } 
    .col-time { width: 50px; }

    /* COMPACT EMPLOYEE CELL */
    .col-emp div {
        display: flex;
        justify-content: space-between;
        align-items: center;
        flex-wrap: nowrap;
    }
    .emp-hours {
        font-size: 8pt !important;
        margin: 0 !important;
        padding: 0 !important;
        border: none !important;
        background: none !important;
        color: #000 !important;
    }
    
    /* SHOW OT TAG ON PRINT */
    .ot-tag { 
        display: inline !important; 
        color: #000 !important; 
        font-weight: bold;
        font-size: 7pt;
        margin-left: 2px;
    }

    /* COMPACT SHIFT CARD (Standard) */
    .shift-card { 
        background: none !important; 
        border: none !important;
        border-bottom: 1px dashed #d1d5db !important;
        padding: 2px 0 !important; 
        margin: 0 !important; 
        box-shadow: none; 
        display: flex !important;
        flex-direction: row !important;
        align-items: center;
        justify-content: center;
        gap: 6px;
        flex-wrap: nowrap;
        min-height: 0 !important; /* Ensure standard cards don't force height either */
    }
    
    /* JOB ONLY CARD FIX (Specific overrides) */
    .shift-card.job-only {
        min-height: 0 !important;        /* Kill the 56px screen height */
        height: auto !important;         /* Let it shrink to text size */
        padding: 2px 0 !important;       /* Match standard shift padding */
        background: none !important;     /* Remove blue background */
        border: none !important;         /* Remove box border */
        border-bottom: 1px dashed #d1d5db !important; /* Add the same underline as other shifts */
        display: flex !important;
        align-items: center;
        justify-content: center;
        box-shadow: none !important;
    }

    .shift-card.job-only .job-only-label {
        font-size: 9pt !important;       /* Match shift text size (small) */
        color: #000 !important;          /* Black text */
        font-weight: bold !important;
        letter-spacing: 0;               /* Remove extra spacing to save space */
    }
    
    /* Double check buttons are hidden */
    .shift-card.job-only .btn-delete, 
    .shift-card.job-only .tooltip-trigger {
        display: none !important;
    }

    .shift-time { 
        color: #000 !important; 
        font-weight: bold; 
        font-size: 9pt !important; 
        margin: 0 !important;
        white-space: nowrap;
    }
    
    .shift-details { 
        color: #374151 !important; 
        font-size: 8pt !important;
        display: inline-block !important;
    }
    
    .shift-job-badge {
        background: none !important;
        color: #000 !important;
        border: none !important;
        padding: 0 !important;
        font-size: 8pt !important;
        margin: 0 !important;
        font-weight: normal;
        font-style: italic;
    }
    .shift-job-badge span { display: none !important; } 

    /* Hide Extra Elements */
/* Show the name, but hide the 'X' button */
.task-chip { 
    display: inline-flex !important; 
    color: black !important; 
    border: 1px solid #ccc !important; 
}
.task-chip span { display: none !important; }
    td.unavailable { background-color: #e5e7eb !important; }
    .status-ok, .status-over, .status-under { border: none; color: #000; }
}

.add-staff-group {
    display: flex;
    align-items: stretch;
    margin-bottom: 10px;
}

.add-staff-group input {
    margin-bottom: 0 !important; /* Overrides global input margin */
    border-top-right-radius: 0;
    border-bottom-right-radius: 0;
    border-right: none; 
}

.add-staff-group button {
    width: auto;         /* Allow button to fit text */
    margin: 0 !important; /* Remove top margin */
    border-top-left-radius: 0;
    border-bottom-left-radius: 0;
    padding: 0 20px;     /* Wider click area */
}


/* --- TOOLTIP STYLES --- */
.tooltip-trigger {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    width: 18px;
    height: 18px;
    background: #9ca3af; /* Gray circle */
    color: white;
    border-radius: 50%;
    font-size: 11px;
    font-weight: bold;
    margin-left: 8px;
    cursor: help;
    position: relative;
    vertical-align: middle;
    text-transform: none;
}

.tooltip-trigger:hover { background: var(--primary); }

.tooltip-content {
    display: none; /* Hidden by default */
    position: absolute;
    top: 24px;
    right: -5px; /* Aligns popup to the right edge of the icon */
    width: 220px;
    background: #1f2937; /* Dark slate */
    color: white;
    padding: 10px;
    border-radius: 6px;
    font-size: 0.75rem;
    font-weight: normal;
    line-height: 1.4;
    z-index: 1000;
    box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.2);
    text-align: left;
    white-space: normal;
}

/* Little arrow pointing up */
.tooltip-content::after {
    content: "";
    position: absolute;
    bottom: 100%;
    right: 8px;
    border-width: 5px;
    border-style: solid;
    border-color: transparent transparent #1f2937 transparent;
}

/* Show on hover */
.tooltip-trigger:hover .tooltip-content { display: block; }

/* HIDE WHEN DISABLED */
body.tooltips-disabled .tooltip-trigger { display: none !important; }

/* Variation: Force tooltip to open to the Right */
.tooltip-trigger.open-right .tooltip-content {
    right: auto;      /* Unset the default right alignment */
    left: -5px;       /* Anchor left edge to the icon */
}

/* Move the little arrow to the left side */
.tooltip-trigger.open-right .tooltip-content::after {
    right: auto;
    left: 8px;
}

/* Ensure the columns allow layering */
.sidebar-col, .schedule-column {
    position: relative;
}

/* Set the Layer Order: Left = Highest, Right = Lowest */
/* Left Sidebar (Staff Pool) - Sits on top of everything */
.main-layout > div:nth-child(1) { z-index: 30; }

/* Middle Sidebar (Configure Shift) - Sits under Left, but on top of Schedule */
.main-layout > div:nth-child(2) { z-index: 20; }

/* Right Area (Schedule Grid) - Sits on bottom */
.main-layout > div:nth-child(3) { z-index: 10; }

/* --- SHIFT CARD TOOLTIPS --- */

/* Allow the table to show popups outside its box */
.week-container {
    overflow: visible !important; 
}

/* Z-Index Boost: Brings the hovered card to the front so the popup floats OVER other shifts */
.shift-card:hover {
    z-index: 100;
    border-color: var(--primary); /* Optional: Highlights card on hover */
}

/* Mini Trigger Style (Smaller than the main headers) */
.tooltip-trigger.shift-tip {
    position: absolute;  /* Takes it out of the text flow */
    top: 4px;            /* 4px from the top edge */
    right: 4px;          /* 4px from the right edge */
    width: 14px;
    height: 14px;
    font-size: 9px;
    background: #e5e7eb; 
    color: #374151;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: help;
    z-index: 10;         /* Ensures it sits above the background */
    margin: 0;           /* Remove old margins */
}

/* Hover State */
.tooltip-trigger.shift-tip:hover {
    background: var(--primary);
    color: white;
}

/* Popup Positioning: Force it ABOVE the shift */
.tooltip-trigger.shift-tip .tooltip-content {
    width: 140px;
    top: auto;        /* Unset default top */
    bottom: 125%;     /* Push it up above the icon */
    left: 50%;        /* Center horizontally */
    right: auto;
    transform: translateX(-50%); /* Perfect centering */
    text-align: center;
}

/* Arrow pointing down (since box is above) */
.tooltip-trigger.shift-tip .tooltip-content::after {
    top: 100%;        /* Bottom of box */
    bottom: auto;
    left: 50%;
    right: auto;
    margin-left: -5px; /* Center the arrow */
    border-color: #1f2937 transparent transparent transparent;
}

/* PAID HOLIDAY STYLES - REVISED */
.shift-card.is-holiday {
    background: #faf5ff !important; 
    border: 1px solid #d8b4fe !important;
    border-left: 4px solid #9333ea !important;
}

/* Remove the badge background in standard view too */
.shift-card.is-holiday .holiday-text {
    background: none !important;
    color: #9333ea !important;
    font-weight: bold;
}

/* Hourly View Chip for Holidays */
.hour-chip.is-holiday {
    background: #faf5ff;
    border-left: 3px solid #9333ea;
    color: #6b21a8;
}

/* JOB ONLY SHIFT STYLES */
.shift-card.job-only {
    background: #eef2ff !important;
    border: 1px solid #c7d2fe !important;
    border-left: 4px solid #6366f1 !important; /* Indigo */
    color: #4338ca !important;

    /* Make it look like a full shift card */
    padding: 8px 10px;
    min-height: 56px; /* Matches the approximate height of standard shifts */
    
    /* Center the label text */
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative; /* Anchor for the buttons */
}

/* Hide standard elements inside a job-only card */
.shift-card.job-only .shift-time,
.shift-card.job-only .shift-details,
.shift-card.job-only .shift-job-badge {
    display: none !important;
}

/* Style the Label */
.shift-card.job-only .job-only-label {
    display: block;
    font-size: 0.95rem;
    font-weight: 800;
    text-transform: uppercase;
    letter-spacing: 0.5px;
    text-align: center;
    width: 100%;
}

/* Fix controls to stay in corners for Job Only cards */
/* This prevents them from pushing the centered text around */
.shift-card.job-only .btn-delete {
    position: absolute;
    top: 4px;
    left: 4px;
    margin: 0;
}

.shift-card.job-only .tooltip-trigger {
    position: absolute;
    top: 4px;
    right: 4px;
    margin: 0;
}

/* --- DYNAMIC PRINT TOGGLES --- */

/* Hide specific elements based on body classes */
body.hide-lunch-print .shift-details { display: none !important; }
body.hide-jobs-print .shift-job-badge:not(.holiday-badge) { display: none !important; }

@media print {
    /* If everything is hidden, make the remaining shift time larger and centered */
    body.hide-lunch-print.hide-jobs-print .shift-time {
        font-size: 13pt !important;
        font-weight: 800 !important;
        width: 100%;
        text-align: center;
        margin: 0 !important;
    }

    body.hide-lunch-print.hide-jobs-print .shift-card {
        min-height: 35px !important;
        display: flex !important;
        align-items: center;
        justify-content: center;
        border-bottom: none !important;
    }
}

/* Remove badge/outline styling for Holiday Text */
.holiday-text {
    background: none !important;
    border: none !important;
    color: #581c87 !important; /* Keep purple color but remove background */
    font-weight: 800 !important;
    font-size: 0.75rem !important;
    padding: 0 !important;
    margin-top: 2px !important;
    display: inline-block !important;
    text-transform: uppercase;
}

    </style>
</head>
<body>

    <div class="header">
        <h1>Schedule Me Scheduler</h1>
        <div class="header-controls">
   	    <div class="view-toggle">
                <button id="btn-hourly" onclick="switchView('hourly')">Hourly</button>
                <button id="btn-daily" onclick="switchView('daily')">Daily</button>
                <button id="btn-weekly" class="active" onclick="switchView('weekly')">Weekly</button>
                <button id="btn-monthly" onclick="switchView('monthly')">Monthly</button>
		<button id="btn-tasks" onclick="switchView('tasks')">Tasks</button>
            </div>
            <div class="nav-group">
                <button onclick="changeDate(-1)">&#9664;</button>
                <input type="date" id="start-date-picker" onchange="renderAll()">
                <button onclick="changeDate(1)">&#9654;</button>
            </div>
<div id="print-options-group" style="display:flex; gap:12px; align-items:center; margin-right:15px; padding-right:15px; border-right:1px solid #d1d5db;">
    <span style="font-size:0.75rem; font-weight:bold; color:var(--text-muted); text-transform:uppercase;">Print:</span>
    <label style="font-size:0.8rem; cursor:pointer; display:flex; align-items:center; gap:4px;">
        <input type="checkbox" id="opt-hide-lunch" onchange="updatePrintClasses()" checked> Lunch
    </label>
    <label style="font-size:0.8rem; cursor:pointer; display:flex; align-items:center; gap:4px;">
        <input type="checkbox" id="opt-hide-jobs" onchange="updatePrintClasses()" checked> Jobs
    </label>
</div>
            <button class="primary" style="margin:0; width:auto; padding: 8px 16px;" onclick="window.print()">
                <span id="publish-status">Print / PDF</span>
            </button>
	<button id="btn-toggle-help" style="margin:0; margin-left:10px; padding: 8px 12px; font-size:0.8rem; background:white; color:#6b7280; border:1px solid #d1d5db;" 	onclick="toggleHelp()">
    	Hide Help
	</button>
        </div>
    </div>

    <div class="main-layout">
<div class="sidebar-col">
            <div class="sticky-wrapper">
                
                <div class="panel">
                    <h3>Staff Pool 
    		<span class="tooltip-trigger open-right">?
        		<div class="tooltip-content">
           		 <strong>Add Employees:</strong> Type a name and press enter.<br><br>
            		<strong>Assigning:</strong> Drag names from here onto the schedule grid to create a shift for that person.
        		</div>
   		 </span>
		</h3>
                    <div class="add-staff-group">
                        <input type="text" id="new-emp-name" placeholder="Name..." onkeypress="if(event.key==='Enter') addEmployee()">
                        <button class="primary" onclick="addEmployee()">ADD</button>
                    </div>
                    <div id="staff-list" class="staff-pool-list"></div>
                </div>

                <div class="panel">
                    <h3>Job / Station 
    		<span class="tooltip-trigger open-right">?
        		<div class="tooltip-content">
            		<strong>Job Labels:</strong> Create specific roles (e.g., "Role A", "Station 1").<br><br>
            		<strong>Usage:</strong> Drag a job pill onto an existing shift on the grid to assign that role.
        		</div>
    		</span>
		</h3>
                    <div class="add-staff-group">
                        <input type="text" id="new-job-name" placeholder="Job Name..." onkeypress="if(event.key==='Enter') addJob()">
                        <button class="primary" onclick="addJob()">ADD</button>
                    </div>
                    <div id="job-list" class="favorites-list"></div>
                </div>

            </div>
        </div>

        <div class="sidebar-col">
            <div class="sticky-wrapper">
<div class="panel">
                    <h3>Configure Shift 
    		<span class="tooltip-trigger open-right">?
        		<div class="tooltip-content">
            		<strong>1. Select Time:</strong> Use the dropdowns to pick start/end times.<br>
            		<strong>2. Assign:</strong> Drag the "Drag to Assign" box onto the grid to create a shift with those times.<br>
            		<strong>3. Default Job:</strong> Drag a Job Pill into the dotted box below to auto-assign that job to new shifts.
        		</div>
    		</span>
		</h3>
                    <div class="draggable-shift-source" draggable="true" ondragstart="shiftDragStart(event)">
                        <span class="source-icon">⁝</span> Drag to Assign
                    </div>

<div class="control-group">
                        <label>Shift Time (Select in Dropdown)</label>
                        <div class="time-row">
                            <div class="time-selects"><select id="start-hour"></select><select id="start-min"></select></div>
                            <span style="margin:0 5px;">to</span>
                            <div class="time-selects"><select id="end-hour"></select><select id="end-min"></select></div>
                        </div>
                    </div>

                    <div id="config-job-display" 
                         ondrop="configJobDrop(event)" 
                         ondragover="configJobDragOver(event)" 
                         ondragleave="configJobDragLeave(event)"
                         style="border: 2px dashed #cbd5e1; border-radius: 6px; padding: 10px; text-align: center; margin-bottom: 15px; background: #f8fafc; color: #64748b; font-size: 0.85rem; transition: all 0.2s;">
                        Drag Job Here to Set Default
                    </div>
                    <div id="message-box"></div>
                </div>

                <div class="panel">
                    <h3>Shift Favorites 
    		<span class="tooltip-trigger open-right">?
        		<div class="tooltip-content">
           		 <strong>Save Templates:</strong> Drag the "Drag to Assign" box (from above) into this area to save that specific time range for quick reuse later.
        		</div>
    		</span>
		</h3>
                    <div class="favorites-drop-zone" ondrop="favoritesDropHandler(event)" ondragover="favoritesDragOver(event)" ondragleave="favoritesDragLeave(event)">
                        + Drop "Drag to Assign" shift here to save
                    </div>
                    <div id="favorites-list" class="favorites-list"></div>
                </div>
            </div>
        </div>

<div class="schedule-column">
            
<div class="data-management-bar">
    <div style="display:flex; align-items:center; gap:5px; margin-right:auto; border-right:1px solid #e5e7eb; padding-right:15px;">
        <label style="margin:0; font-size:0.8rem; color:#6b7280;">Schedule:</label>
        
        <select id="schedule-slot-select" onchange="switchScheduleSlot(this.value)" style="width:150px; margin:0; padding:4px 8px; font-weight:bold; color:#1f2937;"></select>
        
        <button onclick="addNewScheduleSlot()" title="New Schedule" style="width:30px; padding:0; height:30px; background:#dcfce7; color:#166534; border:1px solid #86efac;">+</button>
        
        <button onclick="deleteCurrentSlot()" title="Delete Current" style="width:30px; padding:0; height:30px; background:#fee2e2; color:#991b1b; border:1px solid #fca5a5;">🗑</button>
    </div>
    		<button id="btn-export" class="action-btn" onclick="exportData()">💾 Export</button>
		<button id="btn-import" class="action-btn" onclick="document.getElementById('import-file').click()">📂 Import</button>
		<button class="action-btn" style="background:#4f46e5;" onclick="openShareModal()">☁ Share</button>
		<input type="file" id="import-file" style="display:none" onchange="importData(this)">
                
                <div style="width: 1px; height: 24px; background: var(--border); margin: 0 5px;"></div> <button class="danger-btn" style="width:auto; margin:0; padding: 8px 16px;" onclick="clearStaffPool()">∅ Clear Staff</button>
                <button class="danger-btn" style="background:#fff; color:var(--danger); width:auto; margin:0; padding: 8px 16px;" onclick="resetSystem()">⚠ Reset Schedule</button>
            </div>

            <div id="schedule-container"></div>
        </div>
    </div>

    <dialog id="config-modal">
        <h3 id="modal-emp-name">Configure Employee</h3>
        <p style="font-size:0.8rem; color:var(--text-muted); margin-top:-10px;">For Week of <span id="modal-week-date"></span></p>
        <form method="dialog">
            <div class="control-group">
                <label>Weekly Limit (Max 40)</label>
                <input type="number" id="modal-max-hours" value="40" min="1" max="40">
            </div>
            <div class="control-group">
                <label>Blackout Days</label>
                <div class="day-checkboxes">
                    <label><input type="checkbox" name="blackout" value="Monday"> Mon</label>
                    <label><input type="checkbox" name="blackout" value="Tuesday"> Tue</label>
                    <label><input type="checkbox" name="blackout" value="Wednesday"> Wed</label>
                    <label><input type="checkbox" name="blackout" value="Thursday"> Thu</label>
                    <label><input type="checkbox" name="blackout" value="Friday"> Fri</label>
                    <label><input type="checkbox" name="blackout" value="Saturday"> Sat</label>
                </div>
            </div>
            <div class="dialog-buttons">
                <button class="primary" id="btn-save-config" type="button">Save & Add</button>
                <button onclick="closeModal()" type="button">Cancel</button>
            </div>
        </form>
    </dialog>

<dialog id="lunch-modal">
    <h3>Edit Shift Details</h3>
    <p style="font-size:0.8rem; color:var(--text-muted); margin-top:-10px;">For <span id="lunch-emp-name" style="font-weight:bold; color:var(--text-main);"></span></p>
    <form method="dialog">
        
<form method="dialog">
        
        <div class="control-group" style="margin-bottom: 10px; padding: 10px; background: #f3f4f6; border-radius: 6px;">
            <label style="display:flex; align-items:center; gap:8px; cursor:pointer; margin:0; color:var(--text-main);">
                <input type="checkbox" id="modal-shift-holiday" style="width:auto; margin:0; accent-color: #9333ea;"> 
                Paid Holiday (Non-Working)
            </label>
        </div>

        <div class="control-group">
            <label>Job / Station</label>
            <select id="modal-shift-job" style="width:100%; font-weight:bold;">
                <option value="">(None)</option>
            </select>
        </div>

        <div class="control-group">
            <label>Lunch Start Time</label>
            <div class="time-row">
                <div class="time-selects">
                    <select id="modal-lunch-hour"></select>
                    <select id="modal-lunch-min"></select>
                </div>
            </div>
        </div>
        <div class="control-group">
            <label>Lunch Duration</label>
            <select id="modal-lunch-duration" style="width:100%">
                <option value="0">No Lunch</option>
                <option value="0.25">15 Min</option>
                <option value="0.5">30 Min</option>
                <option value="0.75">45 Min</option>
                <option value="1.0">1 Hr</option>
            </select>
        </div>
        <div class="dialog-buttons">
            <button class="primary" id="btn-save-lunch" type="button">Save Changes</button>
            <button onclick="document.getElementById('lunch-modal').close()" type="button">Cancel</button>
        </div>
    </form>
</dialog>

<dialog id="task-modal">
    <h3>Manage Task List</h3>
    <div class="control-group">
        <label>Select Category</label>
        <select id="manage-task-cat" onchange="renderTaskManagerList()">
            <option value="Daily">Daily</option>
            <option value="Weekly">Weekly</option>
            <option value="Bi-Weekly">Bi-Weekly</option>
            <option value="Monthly">Monthly</option>
            <option value="As Needed">As Needed</option>
        </select>
    </div>
    
    <div class="control-group">
        <label>Add New Task</label>
        <div class="add-staff-group"> <input type="text" id="new-task-name" placeholder="Task Name" onkeypress="if(event.key==='Enter') addTaskFromModal()">
            <button class="primary" onclick="addTaskFromModal()">ADD</button>
        </div>
    </div>

    <div class="control-group">
        <label>Current Tasks in Category</label>
        <div id="task-manager-list" class="favorites-list" style="height: 200px;"></div>
    </div>

    <div class="dialog-buttons">
        <button onclick="document.getElementById('task-modal').close()" type="button">Close</button>
    </div>
</dialog>

<dialog id="share-modal" style="width: 400px;">
    <h3>Share / Load Schedule</h3>
    <p style="font-size:0.85rem; color:var(--text-muted); margin-top:-10px;">
        Copy this code to share, or paste a code to load.
    </p>

    <div class="control-group">
        <label>Share Code</label>
        <textarea id="share-code-input" rows="6" 
            style="width:100%; font-family:monospace; font-size:0.8rem; padding:8px; border:1px solid var(--border); border-radius:4px; resize:vertical;"
            placeholder="Paste code here..."></textarea>
    </div>

    <div class="dialog-buttons">
        <button class="primary" onclick="loadFromShareCode()">Load Code</button>
        <button onclick="copyShareCode()" style="background:#e0f2fe; color:#0369a1; border:1px solid #bae6fd;">Copy To Clipboard</button>
        <button onclick="document.getElementById('share-modal').close()">Close</button>
    </div>
</dialog>

    <script>
// --- CONFIGURATION & CONSTANTS --- 
    // It validates that the save file matches this specific version of the app.
    const APP_BUILD_SIGNATURE = "ScheduleMe";   // Build signature used to obfuscate/validate stored blobs and maintain compatibility
    
    const OVERTIME_THRESHOLD = 40.0;  // Weekly overtime threshold (hours) used for status/labels
    const WEEKDAYS = ["Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"];  // Weekday display labels used when rendering schedules and computing day names
    
    const DEFAULT_TASKS = {  // Default task library grouped by recurrence category for the Tasks view
        "Daily": [  // Configuration object property for: Daily
        ],   
        "Weekly": [  // Configuration object property for: Weekly
        ],   
        "Bi-Weekly": [  // Configuration object property for: Bi-Weekly
	],  
        "Monthly": [  // Configuration object property for: Monthly
        ],   
        "As Needed": [  // Configuration object property for: As Needed
        ]   
    };   

// --- DATA VARIABLES ---
    let staffPool = [];  // In-memory list of employees available to schedule (drag source)
    let weeklyRoster = [];   // Per-week roster entries (employee added to a specific week with limits/blackouts)
    let schedule = [];   // All scheduled shifts (each shift includes employee, date, times, job, lunch, etc.)
    let shiftFavorites = [];  // Saved shift templates for quick drag-and-drop assignment
    let pendingRosterUniqueId = null;  // Define state variable: pending roster unique id
    let dailyNotes = {};  // Map of date -> freeform note displayed on daily/weekly views
    let jobList = [];  // List of job/station labels used for default job and per-shift job assignment
    let currentConfigJob = null;  // Current default job/station applied to newly created shifts (set via drag-drop)
    let taskAssignments = {};  // Map of (date, task, category) -> assigned employee for Tasks view
    let currentView = 'weekly';   // Active UI view (hourly/daily/weekly/monthly/tasks)
    let pendingEmpId = null;  // Define state variable: pending emp id
    let clipboardSchedule = null;  // Temporary in-memory copy used for copy/paste operations between weeks
    let pendingWeekStart = null;  // Define state variable: pending week start
    let pendingLunchShiftId = null;  // Define state variable: pending lunch shift id

    // This variable will hold the live, editable data
    let tasksData = {};  // Task definitions currently in use (editable copy of DEFAULT_TASKS)
    let currentSlot = "Main";   // Currently selected schedule slot name (e.g., Main, Holiday Week)

// --- TOOLTIP SYSTEM ---
function toggleHelp() {
    document.body.classList.toggle('tooltips-disabled');
    const isDisabled = document.body.classList.contains('tooltips-disabled');
    localStorage.setItem('schme_tooltips_disabled', isDisabled);
    updateHelpButton(isDisabled);
}

function updateHelpButton(isDisabled) {
    const btn = document.getElementById('btn-toggle-help');
    if(btn) btn.innerHTML = isDisabled ? "Show Help" : "Hide Help";
}

function initTooltips() {
    const isDisabled = localStorage.getItem('schme_tooltips_disabled') === 'true';
    if(isDisabled) document.body.classList.add('tooltips-disabled');
    updateHelpButton(isDisabled);
}

// --- DATA SERIALIZATION MODULE ---

    // Storage is intentionally obfuscated (XOR + base64) so it is not human-readable at a glance.
    // This version is UTF-8 safe (supports emojis / non‑ASCII characters).
    //
    // Formats supported:
    // - SCHME:  (current) UTF-8 bytes XOR signature bytes, base64
    // - Legacy:   (legacy) char XOR signature chars, base64
    // - plain JSON (legacy)
    function serializeStorageBlob(dataObj) {  // Define function: serialize storage blob
        try {  // Begin error-handling block
            const jsonString = JSON.stringify(dataObj);  // Define constant: json string

            const jsonBytes = new TextEncoder().encode(jsonString);  // Define constant: json bytes
            const sigBytes = new TextEncoder().encode(APP_BUILD_SIGNATURE);  // Define constant: sig bytes

            const outBytes = new Uint8Array(jsonBytes.length);  // Define constant: out bytes
            for (let i = 0; i < jsonBytes.length; i++) {  // Loop over a range/collection to process items
                outBytes[i] = jsonBytes[i] ^ sigBytes[i % sigBytes.length];  
            }   

            // Base64 encode bytes (safe for all byte values 0-255)
            let binary = '';  // Define state variable: binary
            for (let i = 0; i < outBytes.length; i++) {  // Loop over a range/collection to process items
                binary += String.fromCharCode(outBytes[i]);  
            }   

            return 'SCHME:' + btoa(binary);  // Return a value/exit point for this function
        } catch (e) {  // Begin block scope
            console.error("Serialization failed:", e);  
            return null;  // Return a value/exit point for this function
        }   
    }   

    function parseStorageBlob(rawStream) {  // Parse/validate input data: storage blob
        try {  // Begin error-handling block
            if (typeof rawStream !== 'string') {  // Conditional guard/check before executing the next block
                throw new Error("Invalid stream type");  
            }   

            // Current UTF-8 safe format
            if (rawStream.startsWith('SCHME:')) {  // Conditional guard/check before executing the next block
                const base64 = rawStream.substring(9);  // Define constant: base64
                const binary = atob(base64);  // Define constant: binary
                const bytes = new Uint8Array(binary.length);  // Define constant: bytes
                for (let i = 0; i < binary.length; i++) {  // Loop over a range/collection to process items
                    bytes[i] = binary.charCodeAt(i);  
                }   

                const sigBytes = new TextEncoder().encode(APP_BUILD_SIGNATURE);  // Define constant: sig bytes
                const outBytes = new Uint8Array(bytes.length);  // Define constant: out bytes
                for (let i = 0; i < bytes.length; i++) {  // Loop over a range/collection to process items
                    outBytes[i] = bytes[i] ^ sigBytes[i % sigBytes.length];  
                }   

                const jsonString = new TextDecoder().decode(outBytes);  // Define constant: json string
                return JSON.parse(jsonString);  // Return a value/exit point for this function
            }   

            // Legacy format (kept for backwards compatibility)
            if (rawStream.startsWith('Legacy:')) {  // Conditional guard/check before executing the next block
                const rawBuffer = atob(rawStream.substring(8));  // Define constant: raw buffer
                let resultString = '';  // Define state variable: result string
                for (let i = 0; i < rawBuffer.length; i++) {  // Loop over a range/collection to process items
                    resultString += String.fromCharCode(  
                        rawBuffer.charCodeAt(i) ^ APP_BUILD_SIGNATURE.charCodeAt(i % APP_BUILD_SIGNATURE.length)  
                    );   
                }   
                return JSON.parse(resultString);  // Return a value/exit point for this function
            }   

            // Legacy: plain JSON
            return JSON.parse(rawStream);  // Return a value/exit point for this function

        } catch (e) {  // Begin block scope
            console.error("Blob parsing error:", e);  
            // Alert user that the data is incompatible
            alert("Error loading data: The save file is not compatible with this version of the software.");  // Show an alert dialog to the user
            return null;  // Return a value/exit point for this function
        }   
    }

// --- SIMPLIFIED PRINT ---
function toggleSimplifiedPrint() {
    const isChecked = document.getElementById('simplified-print-checkbox').checked;
    if (isChecked) {
        document.body.classList.add('simplified-print-active');
    } else {
        document.body.classList.remove('simplified-print-active');
    }
    // Re-render is not strictly needed because CSS handles it, 
    // but we call renderAll to ensure any dynamic spacing updates.
    renderAll(); 
}

function updatePrintClasses() {
    const hideLunch = !document.getElementById('opt-hide-lunch').checked;
    const hideJobs = !document.getElementById('opt-hide-jobs').checked;

    // Toggle classes on body based on checkbox state
    document.body.classList.toggle('hide-lunch-print', hideLunch);
    document.body.classList.toggle('hide-jobs-print', hideJobs);

    // Refresh the view
    renderAll();
}

// Run once on load to set initial state
window.addEventListener('DOMContentLoaded', updatePrintClasses);

// --- SCHEDULE SLOT MANAGEMENT ---
    let availableSlots = ["Main"];   // List of defined schedule slots stored in localStorage

    function loadSlotList() {  // Load persisted/app data: slot list
        const stored = localStorage.getItem('scheduler_slots_list');  // Define constant: stored
        if (stored) {  // Conditional guard/check before executing the next block
            availableSlots = JSON.parse(stored);  // Parse a JSON string into a JS object
        } else {   
            availableSlots = ["Main"];  
        }   
        renderSlotSelector();  
    }

    function renderSlotSelector() {  // Render UI for: slot selector
        const sel = document.getElementById('schedule-slot-select');  // Define constant: sel
        sel.innerHTML = '';  
        availableSlots.forEach(slot => {  // Iterate over array elements
            const opt = document.createElement('option');  // Define constant: opt
            opt.value = slot;  
            opt.innerText = slot;  // Set text content for a DOM element
            if(slot === currentSlot) opt.selected = true;  // Conditional guard/check before executing the next block
            sel.appendChild(opt);  // Append a child node into the DOM
        });   
    }

    function addNewScheduleSlot() {  // Add/create: new schedule slot
        const name = prompt("Enter a name for the new schedule (e.g. 'Holiday Week'):");  // Define constant: name
        if (!name) return;  // Conditional guard/check before executing the next block
        const cleanName = name.trim();  // Define constant: clean name
        if (availableSlots.includes(cleanName)) {  // Conditional guard/check before executing the next block
            alert("A schedule with that name already exists.");  // Show an alert dialog to the user
            return;  // Return a value/exit point for this function
        }

        saveState();  
        availableSlots.push(cleanName);  // Append a new item to an array (update scheduler data)
        localStorage.setItem('scheduler_slots_list', JSON.stringify(availableSlots));  // Persist a value into browser localStorage
        currentSlot = cleanName;  
        renderSlotSelector();  
        loadState();  
        renderStaffPool();  
        renderFavorites();  
        renderJobList();  
        renderAll();  
    }

    function deleteCurrentSlot() {  // Remove/delete: delete current slot
        if (currentSlot === "Main") {  // Conditional guard/check before executing the next block
            alert("You cannot delete the Main Schedule. Please clear it instead if you wish to start over.");  // Show an alert dialog to the user
            return;  // Return a value/exit point for this function
        }         

	if (!confirm(`Are you sure you want to PERMANENTLY delete "${currentSlot}"?`)) return;  // Conditional guard/check before executing the next block
        
        const storageKey = 'schedulerData_' + currentSlot;  // Define constant: storage key
        localStorage.removeItem(storageKey);  // Delete a key from browser localStorage
        
        availableSlots = availableSlots.filter(s => s !== currentSlot);  // Create a filtered copy of an array based on a predicate
        localStorage.setItem('scheduler_slots_list', JSON.stringify(availableSlots));  // Persist a value into browser localStorage
        
        currentSlot = "Main";  
        renderSlotSelector();  
        loadState();  
        renderStaffPool();  
        renderFavorites();  
        renderJobList();  
        renderAll();  
        showMessage("Schedule deleted.", "success");  
    } 

    function switchScheduleSlot(newSlot) {  // Switch UI/data context: schedule slot
        if(currentSlot === newSlot) return;  // Conditional guard/check before executing the next block
        saveState();  
        currentSlot = newSlot;  
        loadState();  
        clipboardSchedule = null;  
        renderSlotSelector();  
        renderStaffPool();  
        renderFavorites();  
        renderJobList();  
        if (currentView === 'tasks') renderTasksView();  // Conditional guard/check before executing the next block
        else renderAll();   
        showMessage(`Switched to ${newSlot}`, "success");  
    } 

// --- INIT & PERSISTENCE ---
    function init() {  // Define function: init
	initTooltips();        
	loadSlotList();  
        const today = new Date();  // Define constant: today
        const day = today.getDay();  // Define constant: day
        const diff = today.getDate() - day + (day === 0 ? -6 : 1);   // Define constant: diff
        const monday = new Date(today.setDate(diff));  // Define constant: monday
        document.getElementById('start-date-picker').valueAsDate = monday;  // Lookup DOM element by id: #start-date-picker

        populateTimeSelects();  
        loadState();   
        renderStaffPool();  
        renderFavorites();  
        renderJobList();  
        switchView(currentView);  

        const saveConfigBtn = document.getElementById('btn-save-config');  // Define constant: save config btn
        if(saveConfigBtn) saveConfigBtn.onclick = saveRosterConfig;  // Conditional guard/check before executing the next block
    }

    function saveState() {  // Save/persist data: state
        const storageKey = currentSlot === "Main" ? 'schedulerData' : 'schedulerData_' + currentSlot;  // Define constant: storage key

        const data = {   // Define constant: data
            staffPool, weeklyRoster, schedule, currentView,   
            shiftFavorites, dailyNotes, jobList, taskAssignments, tasksData   
        };   
        
        // USE SERIALIZER
        const formattedData = serializeStorageBlob(data);  // Define constant: formatted data
        
        if (formattedData) {  // Conditional guard/check before executing the next block
            localStorage.setItem(storageKey, formattedData);  // Persist a value into browser localStorage
        }   
    }   

    function loadState() {  // Load persisted/app data: state
        const storageKey = currentSlot === "Main" ? 'schedulerData' : 'schedulerData_' + currentSlot;  // Define constant: storage key
        const storedItem = localStorage.getItem(storageKey);  // Define constant: stored item
        
        if (storedItem) {  // Conditional guard/check before executing the next block
            // USE PARSER
            const data = parseStorageBlob(storedItem);  // Define constant: data
            
            if (data) {  // Conditional guard/check before executing the next block
                staffPool = data.staffPool || [];  
                weeklyRoster = data.weeklyRoster || [];  
                schedule = data.schedule || [];  
                shiftFavorites = data.shiftFavorites || [];  
                currentView = data.currentView || 'weekly';  
                dailyNotes = data.dailyNotes || {};  
                jobList = data.jobList || [];  
                taskAssignments = data.taskAssignments || {};  
                tasksData = data.tasksData || JSON.parse(JSON.stringify(DEFAULT_TASKS));  // Serialize a JS object to a JSON string
            }   
        } else {   
            // Fresh Start
            staffPool = [];   
            schedule = [];  
            weeklyRoster = [];  
            dailyNotes = {};  
            taskAssignments = {};  
            jobList = [];   
            tasksData = JSON.parse(JSON.stringify(DEFAULT_TASKS));   // Serialize a JS object to a JSON string
        }   
    }   

// --- STAFF MANAGEMENT ---
    function renderStaffPool() {  // Render UI for: staff pool
        const container = document.getElementById('staff-list');  // Define constant: container
        if(!container) return;  // Conditional guard/check before executing the next block
        container.innerHTML = '';  
        staffPool.forEach(emp => {  // Iterate over array elements
            const div = document.createElement('div');  // Define constant: div
            div.className = 'draggable-emp';   
            div.draggable = true;   
            div.ondragstart = (ev) => staffDragStart(ev, emp.id);  
            div.innerHTML = `  
                <div class="emp-content" style="flex:1;">${escapeHTML(emp.name)}</div>
                <div style="display:flex; align-items:center;">
                    <button class="btn-edit-staff" onclick="renameStaff(${emp.id})" title="Rename">✎</button>
                    <button class="btn-remove-staff" onclick="removeStaffFromPool(${emp.id})" title="Remove">×</button>
                </div>
            `;  // End of template literal (HTML snippet) used for UI rendering
            container.appendChild(div);  // Append a child node into the DOM
        });   
    }   

    function renameStaff(id) {  // Define function: rename staff
        const emp = staffPool.find(e => e.id === id);  // Define constant: emp
        if (!emp) return;  // Conditional guard/check before executing the next block
        const newName = prompt(`Rename ${emp.name} to:`, emp.name);  // Define constant: new name
        if (newName && newName.trim().length > 0) {  // Conditional guard/check before executing the next block
            emp.name = newName.trim();  
            saveState();  
            renderStaffPool();   
            renderAll();         
        }   
    }   

    function addEmployee() {  // Add/create: employee
        const input = document.getElementById('new-emp-name');  // Define constant: input
        const name = input.value.trim();  // Define constant: name
        if (!name) return;  // Conditional guard/check before executing the next block
        staffPool.push({ id: Date.now(), name: name });  // Append a new item to an array (update scheduler data)
        input.value = '';  
        saveState();  
        renderStaffPool();  
    }   

    function removeStaffFromPool(id) {  // Remove/delete: remove staff from pool
        const emp = staffPool.find(e => e.id === id);  // Define constant: emp
        if (!emp) return;  // Conditional guard/check before executing the next block
        if(!confirm(`Delete ${emp.name} from the Staff Pool?`)) return;  // Conditional guard/check before executing the next block
        staffPool = staffPool.filter(e => e.id !== id);  // Create a filtered copy of an array based on a predicate
        saveState();  
        renderStaffPool();  
        renderAll();   
    }   

    function clearStaffPool() {  // Define function: clear staff pool
        if(!confirm("Delete ALL staff?")) return;  // Conditional guard/check before executing the next block
        staffPool = [];  
        saveState();  
        renderStaffPool();  
        renderAll();   
    }   

// --- GLOBAL ACTIONS ---
    function resetSystem() {  // Define function: reset system
        if(!confirm("Clear the SCHEDULE?")) return;  // Conditional guard/check before executing the next block
        weeklyRoster = [];  
        schedule = [];  
        dailyNotes = {};  
        saveState();  
        renderAll();  
        showMessage("Schedule Cleared.", "success");  
    }   

    function exportData() {  // Define function: export data
        const btn = document.getElementById('btn-export');  // Define constant: btn
        const originalText = btn.innerHTML;  // Define constant: original text
        btn.innerHTML = "⏳ Please Wait...";  
        btn.disabled = true;  
        btn.style.opacity = "0.7";  // Set inline styles to reflect UI state (e.g., drag-over, warnings)

        setTimeout(() => {  // Begin block scope
            try {  // Begin error-handling block
                // Export is intentionally obfuscated (same idea as local storage) so the file isn't human-readable at a glance.
                const data = {   // Define constant: data
                    staffPool, weeklyRoster, schedule, currentView,   
                    shiftFavorites, dailyNotes, jobList, taskAssignments,   
                    tasksData,  
                    exportDate: new Date().toISOString()   // Create/compute a Date value
                };   

                const encryptedData = serializeStorageBlob(data);  // Define constant: encrypted data
      const blob = new Blob([encryptedData], {type: 'text/plain'});  // Define constant: blob
                const url = URL.createObjectURL(blob);  // Define constant: url
                const a = document.createElement('a');   // Define constant: a
                a.href = url;   
                a.download = `SCHEDULE_ME_${new Date().toISOString().slice(0,10)}.SCHME`;  // Create/compute a Date value
                document.body.appendChild(a);   // Append a child node into the DOM
                a.click();   
                document.body.removeChild(a);  
            } catch (e) {  // Begin block scope
                console.error("Export failed", e);  
                alert("Export failed: " + e.message);  // Show an alert dialog to the user
            }   
            setTimeout(() => {  // Begin block scope
                btn.innerHTML = originalText;  
                btn.disabled = false;  
                btn.style.opacity = "1";  // Set inline styles to reflect UI state (e.g., drag-over, warnings)
            }, 3000);  
        }, 100);  
    }   

    function importData(input) {  // Define function: import data
        const file = input.files[0];  // Define constant: file
        if(!file) return;  // Conditional guard/check before executing the next block
        const btn = document.getElementById('btn-import');  // Define constant: btn
        const originalText = btn ? btn.innerHTML : "📂 Import";  // Define constant: original text
        if(btn) {  // Conditional guard/check before executing the next block
            btn.innerHTML = "⏳ Please Wait...";  
            btn.disabled = true;  
            btn.style.opacity = "0.7";  // Set inline styles to reflect UI state (e.g., drag-over, warnings)
        }   

        setTimeout(() => {  // Begin block scope
            const reader = new FileReader();  // Define constant: reader
            reader.onload = function(e) {  // Begin block scope
                try {  // Begin error-handling block
                    const data = parseStorageBlob(e.target.result);  // Define constant: data
                    if(data && data.weeklyRoster && data.schedule) {  // Conditional guard/check before executing the next block
                        staffPool = data.staffPool || [];   
                        weeklyRoster = data.weeklyRoster;   
                        schedule = data.schedule;   
                        currentView = data.currentView || 'weekly';   
                        shiftFavorites = data.shiftFavorites || [];  
                        dailyNotes = data.dailyNotes || {};  
                        taskAssignments = data.taskAssignments || {};  
                        jobList = data.jobList || [];  
                        if (data.tasksData) tasksData = data.tasksData;  // Conditional guard/check before executing the next block

                        saveState();   
                        renderStaffPool();   
                        renderFavorites();   
                        renderJobList();  
                        switchView(currentView);   
                        showMessage("Data Imported", "success");  
                    } else {    
                        showMessage("Invalid file", "error");   
                    }   
                } catch(err) {   // Begin block scope
                    console.error(err);  
                    showMessage("Error reading file", "error");   
                } finally {  // Begin block scope
                    setTimeout(() => {  // Begin block scope
                        if(btn) {  // Conditional guard/check before executing the next block
                            btn.innerHTML = originalText;  
                            btn.disabled = false;  
                            btn.style.opacity = "1";  // Set inline styles to reflect UI state (e.g., drag-over, warnings)
                        }   
                        input.value = '';   
                    }, 2000);  
                }   
            };   
            reader.readAsText(file);  
        }, 100);  
    }   

    function switchView(mode) {  // Switch UI/data context: view
        currentView = mode;  
        document.querySelectorAll('.view-toggle button').forEach(b => b.className = '');  // Iterate over array elements
        const btn = document.getElementById('btn-'+mode);  // Define constant: btn
        if(btn) btn.className = 'active';  // Conditional guard/check before executing the next block
        saveState();  
        renderAll();  
    }   

// --- RENDERERS ---
    function renderAll() {  // Render UI for: all
        const container = document.getElementById('schedule-container');  // Define constant: container
        if(!container) return;  // Conditional guard/check before executing the next block
        container.innerHTML = '';  
        
        const startDateInput = document.getElementById('start-date-picker').value;  // Define constant: start date input
        if(!startDateInput) return;  // Conditional guard/check before executing the next block

        if(currentView === 'hourly') {  // Conditional guard/check before executing the next block
            renderHourlyWeek(startDateInput, container);  
        } else if (currentView === 'tasks') {  // Alternative conditional branch
            renderTasksView();  
        } else {   
            const weeks = getWeeksToRender(startDateInput);  // Define constant: weeks
            weeks.forEach(weekDates => {  // Iterate over array elements
                let businessDays = weekDates;  // Define state variable: business days
                if(currentView !== 'daily') {  // Conditional guard/check before executing the next block
                    businessDays = weekDates.filter(d => d.getDay() !== 0);  // Create a filtered copy of an array based on a predicate
                }   
                if (businessDays.length > 0) {  // Conditional guard/check before executing the next block
                    const refDate = new Date(businessDays[0]);   // Define constant: ref date
                    const day = refDate.getDay();   // Define constant: day
                    const diff = refDate.getDate() - day + (day === 0 ? -6 : 1);  // Define constant: diff
                    const anchorDate = new Date(refDate.setDate(diff));  // Define constant: anchor date
                    const weekStartStr = formatDateString(anchorDate);  // Define constant: week start str
                    const tableHTML = buildWeekTable(businessDays, weekStartStr);  // Define constant: table html
                    const div = document.createElement('div');  // Define constant: div
                    div.className = 'week-container';  
                    div.innerHTML = tableHTML;  
                    container.appendChild(div);  // Append a child node into the DOM
                }   
            });   
        }   
    }   

    function renderHourlyWeek(startStr, container) {  // Render UI for: hourly week
        const startDate = new Date(startStr);  // Define constant: start date
        const utcStart = new Date(startDate.getTime() + startDate.getTimezoneOffset() * 60000);  // Define constant: utc start
        let currentDay = new Date(utcStart);  // Define state variable: current day
        const days = [];  // Define constant: days
        for(let d=0; d<7; d++) {  // Loop over a range/collection to process items
            if(currentDay.getDay() !== 0) days.push(new Date(currentDay));   // Conditional guard/check before executing the next block
            currentDay.setDate(currentDay.getDate() + 1);  // Read/update Date components for week/day computations
        }   

        let html = `<table><thead><tr><th class="col-time">Time</th>`;  // Define state variable: html
        days.forEach(d => {  // Iterate over array elements
            const name = getDayName(d).substring(0,3);  // Define constant: name
            const date = (d.getMonth()+1) + '/' + d.getDate();  // Define constant: date
            const dStr = formatDateString(d);  // Define constant: d str
            const note = dailyNotes[dStr] || "";  // Define constant: note

            html += `<th>  
                        <div>${name} ${date} <button class="btn-edit-note" onclick="editDayNote('${dStr}')">✎</button></div>
                        <div class="day-note">${escapeHTML(note)}</div>
                        </th>`;  // End of template literal (HTML snippet) used for UI rendering
        });   
        html += `</tr></thead><tbody>`;  

        for(let h=7; h<=19; h++) {  // Loop over a range/collection to process items
            let displayH = h > 12 ? h - 12 : h;  // Define state variable: display h
            let ampm = h >= 12 ? 'PM' : 'AM';  // Define state variable: ampm
            html += `<tr><td class="col-time">${displayH} ${ampm}</td>`;  
            days.forEach(d => {  // Iterate over array elements
                const dStr = formatDateString(d);  // Define constant: d str
                html += `<td>`;  
                const activeShifts = schedule.filter(s => {  // Define constant: active shifts
                    if(s.dateString !== dStr) return false;  // Conditional guard/check before executing the next block
                    const slotStart = h;  // Define constant: slot start
                    const slotEnd = h + 1;  // Define constant: slot end
                    return (s.start < slotEnd && s.end > slotStart);  // Return a value/exit point for this function
                });   
                activeShifts.forEach(s => {  // Iterate over array elements
                    const emp = staffPool.find(e => e.id === s.empId);  // Define constant: emp
                    if(emp) {  // Conditional guard/check before executing the next block
                        let isLunch = false;  // Define state variable: is lunch
                        if (s.breakDuration > 0 && s.lunchStart) {  // Conditional guard/check before executing the next block
                            const lunchEnd = s.lunchStart + s.breakDuration;  // Define constant: lunch end
                            if (s.lunchStart < (h + 1) && lunchEnd > h) isLunch = true;  // Conditional guard/check before executing the next block
                        }   
                        const chipClass = isLunch ? 'hour-chip on-lunch' : 'hour-chip';  // Define constant: chip class
                        const icon = isLunch ? '☕ ' : '';  // Define constant: icon
                        html += `<span class="${chipClass}" onclick="openLunchModal(${s.id})">${icon}${escapeHTML(emp.name)}</span>`;  
                    }   
                });   
                html += `</td>`;  
            });   
            html += `</tr>`;  
        }   
        html += `</tbody></table>`;  
        const div = document.createElement('div');  // Define constant: div
        div.className = 'week-container';  
        div.innerHTML = html;  
        container.appendChild(div);  // Append a child node into the DOM
    }   

    function getWeeksToRender(startStr) {  // Define function: get weeks to render
        const startDate = new Date(startStr);  // Define constant: start date
        const utcStart = new Date(startDate.getTime() + startDate.getTimezoneOffset() * 60000);  // Define constant: utc start
        const weeks = [];  // Define constant: weeks
        if (currentView === 'daily') {  // Conditional guard/check before executing the next block
            weeks.push([new Date(utcStart)]);  // Append a new item to an array (update scheduler data)
        }    
        else if (currentView === 'weekly' || currentView === 'tasks') {  // Alternative conditional branch
            const week = [];  // Define constant: week
            let currentDay = new Date(utcStart);  // Define state variable: current day
            for(let d=0; d < 7; d++) {  // Loop over a range/collection to process items
                week.push(new Date(currentDay));  // Append a new item to an array (update scheduler data)
                currentDay.setDate(currentDay.getDate() + 1);  // Read/update Date components for week/day computations
            }   
            weeks.push(week);  // Append a new item to an array (update scheduler data)
        }    
        else {   
            const targetMonth = utcStart.getMonth();  // Define constant: target month
            const targetYear = utcStart.getFullYear();  // Define constant: target year
            let runner = new Date(targetYear, targetMonth, 1);  // Define state variable: runner
            let day = runner.getDay();   // Define state variable: day
            if (day === 0) { runner.setDate(2); day = 1; }  // Conditional guard/check before executing the next block
            const diff = day === 0 ? -6 : 1 - day;  // Define constant: diff
            runner.setDate(runner.getDate() + diff);  // Read/update Date components for week/day computations
            for(let w=0; w<6; w++) {  // Loop over a range/collection to process items
                const week = [];  // Define constant: week
                for(let d=0; d < 7; d++) {  // Loop over a range/collection to process items
                    week.push(new Date(runner));  // Append a new item to an array (update scheduler data)
                    runner.setDate(runner.getDate() + 1);  // Read/update Date components for week/day computations
                }   
                const mondayOfWeek = week[0];   // Define constant: monday of week
                if (mondayOfWeek.getMonth() > targetMonth && mondayOfWeek.getFullYear() >= targetYear) break;   // Conditional guard/check before executing the next block
                if (mondayOfWeek.getFullYear() > targetYear) break;  // Conditional guard/check before executing the next block
                weeks.push(week);  // Append a new item to an array (update scheduler data)
            }   
        }   
        return weeks;  // Return a value/exit point for this function
    }   

    function buildWeekTable(dates, weekStartStr) {  // Define function: build week table
        const weekRoster = weeklyRoster.filter(r => r.weekStart === weekStartStr);  // Define constant: week roster
        let html = `<table><thead><tr><th class="col-emp">Employee</th>`;  // Define state variable: html
        dates.forEach(d => {  // Iterate over array elements
            const name = getDayName(d).substring(0,3);  // Define constant: name
            const date = (d.getMonth()+1) + '/' + d.getDate();  // Define constant: date
            const dStr = formatDateString(d);  // Define constant: d str
            const note = dailyNotes[dStr] || "";  // Define constant: note
            html += `<th>  
                        <div>${name} <span style="font-weight:400; font-size:0.8em">${date}</span> 
                        <button class="btn-edit-note" onclick="editDayNote('${dStr}')">✎</button></div>
                        <div class="day-note">${escapeHTML(note)}</div>
                        </th>`;  // End of template literal (HTML snippet) used for UI rendering
        });   
        html += `</tr></thead><tbody>`;  

        let pasteButtonHtml = "";  // Define state variable: paste button html
        if (clipboardSchedule && !weekRoster.some(r => r.empId === clipboardSchedule.empId)) {  // Conditional guard/check before executing the next block
            pasteButtonHtml = `<button onclick="pasteScheduleToWeek('${weekStartStr}')"   
                                style="margin-left:15px; background:#dbeafe; color:#1e40af; border:1px solid #93c5fd; padding:2px 8px; font-size:0.8rem; border-radius:4px;">
                                📋 Paste ${escapeHTML(clipboardSchedule.empName)} Here
                                </button>`;  // End of template literal (HTML snippet) used for UI rendering
        }   

        html += `<tr class="drop-row"><td colspan="${dates.length + 1}"   
            ondrop="rosterDropHandler(event, '${weekStartStr}')" 
            ondragover="rosterDragOver(event)" 
            ondragleave="rosterDragLeave(event)">
            + Drop Staff Here ${pasteButtonHtml}
            </td></tr>`;  // End of template literal (HTML snippet) used for UI rendering

        weekRoster.forEach(rosterEntry => {  // Iterate over array elements
            const emp = staffPool.find(e => e.id === rosterEntry.empId);  // Define constant: emp
            if(!emp) return;   // Conditional guard/check before executing the next block
            const uniqueId = rosterEntry.uniqueId;   // Define constant: unique id
            const weeklyShifts = schedule.filter(s => s.empId === emp.id && dates.some(d => formatDateString(d) === s.dateString));  // Define constant: weekly shifts
            const totalHours = weeklyShifts.reduce((acc, s) => acc + ((s.end - s.start) - s.breakDuration), 0);  // Define constant: total hours
            
            let statusClass = 'status-ok';  // Define state variable: status class
            if(totalHours > OVERTIME_THRESHOLD) statusClass = 'status-over';  // Conditional guard/check before executing the next block
            else if(totalHours < rosterEntry.maxHours - 10) statusClass = 'status-under';  // Alternative conditional branch

            let pasteBtn = "";  // Define state variable: paste btn
            if (clipboardSchedule) {  // Conditional guard/check before executing the next block
                pasteBtn = `<button onclick="pasteSchedule(${emp.id}, '${weekStartStr}')" title="Paste Schedule" style="border:none; background:none; cursor:pointer; font-size:1.1rem;">📋</button>`;  
            }   

            html += `<td>  
                        <div class="emp-drag-handle" draggable="true" ondragstart="duplicateDragStart(event, ${emp.id}, '${weekStartStr}')">
                            <span style="margin-right:auto;">${escapeHTML(emp.name)}</span>
                            <button onclick="openRosterSettings('${uniqueId}')" title="Edit Settings" style="border:none; background:none; cursor:pointer; font-size:1rem; margin-right:2px;">⚙</button>
                            <button onclick="copySchedule(${emp.id}, '${weekStartStr}')" title="Copy Week" style="border:none; background:none; cursor:pointer; font-size:1rem; margin-right:2px;">📑</button>
                            ${pasteBtn}
                            <button onclick="removeRosterEntry('${uniqueId}')" class="btn-delete" style="float:none; font-size:0.7rem; color:var(--text-muted);">(x)</button>
                        </div>
                        <div class="emp-hours ${statusClass}">${totalHours.toFixed(2)} Hrs ${totalHours > OVERTIME_THRESHOLD ? '<span class="ot-tag">(OT)</span>' : ''}</div>
                        </td>`;  // End of template literal (HTML snippet) used for UI rendering

            dates.forEach(d => {  // Iterate over array elements
                const dStr = formatDateString(d);  // Define constant: d str
                const dayName = getDayName(d);  // Define constant: day name
                let cellClass = '';  // Define state variable: cell class
                if(rosterEntry.blackoutDays && rosterEntry.blackoutDays.includes(dayName)) cellClass = 'unavailable';  // Conditional guard/check before executing the next block
                let dragAttr = "";  // Define state variable: drag attr
                if(cellClass !== 'unavailable') {  // Conditional guard/check before executing the next block
                    dragAttr = `ondrop="shiftDropHandler(event, ${emp.id}, '${dStr}', '${weekStartStr}')" ondragover="shiftDragOver(event)" ondragleave="shiftDragLeave(event)"`;  
                }   

                html += `<td class="${cellClass}" ${dragAttr}>`;  
                if(cellClass !== 'unavailable') {  // Conditional guard/check before executing the next block
                    const shifts = schedule.filter(s => s.empId === emp.id && s.dateString === dStr).sort((a,b) => a.start - b.start);  // Define constant: shifts
shifts.forEach(shift => {
                        // Calculate total minutes first
                        const totalMinutes = Math.round(((shift.end - shift.start) - shift.breakDuration) * 60);
                        const hPart = Math.floor(totalMinutes / 60);
                        const mPart = totalMinutes % 60;
                        const durStr = mPart > 0 ? `${hPart}h ${mPart}m` : `${hPart}h`;
                        
                        let lunchText = "";
                        if (shift.breakDuration > 0 && shift.lunchStart) {
                            lunchText = `<span class="shift-details" style="font-size:0.7rem;">L: ${decimalToDisplay(shift.lunchStart)}</span>`;
                        }
                        
                        let jobHtml = "";
                        if(shift.job) {
                            jobHtml = `<div class="shift-job-badge">${escapeHTML(shift.job)} <span style="cursor:pointer; margin-left:3px;" onclick="removeJobFromShift(${shift.id}, event)">×</span></div>`;
                        }

                        const holidayClass = shift.isHoliday ? ' is-holiday' : '';
                        const holidayLabel = shift.isHoliday ? '<span class="holiday-text">HOLIDAY</span>' : '';

                        // --- Job Only Rendering Logic ---
                        const jobOnlyClass = shift.isJobOnly ? ' job-only' : '';
                        const jobOnlyContent = shift.isJobOnly ? `<div class="job-only-label">${escapeHTML(shift.job)}</div>` : '';
                        // -------------------------------------

                        html += `<div class="shift-card${holidayClass}${jobOnlyClass}" draggable="true" 
                                        onclick="openLunchModal(${shift.id})"
                                        ondragover="event.preventDefault()" 
                                        ondrop="handleJobDrop(event, ${shift.id})"
                                        ondragstart="shiftCardDragStart(event, ${shift.id})">
                                    <button class="btn-delete" onclick="event.stopPropagation(); deleteShift(${shift.id})">×</button>
                                    
                                    <span class="tooltip-trigger shift-tip" onclick="event.stopPropagation()">?
                                        <div class="tooltip-content">
                                            Click card to edit<br>shift details.
                                        </div>
                                    </span>
                                    
                                    <span class="shift-time">${decimalToDisplay(shift.start)} - ${decimalToDisplay(shift.end)}</span>
                                    ${holidayLabel}
                                    ${lunchText}
                                    ${jobHtml}
                                    <span class="shift-details">${durStr}</span>
                                    
                                    ${jobOnlyContent}

                                    </div>`;
                    });
                }   
                html += `</td>`;  
            });   
            html += `</tr>`;  
        });   
        html += `</tbody></table>`;  
        return html;  // Return a value/exit point for this function
    }   

// --- FAVORITES LOGIC ---
    function renderFavorites() {  // Render UI for: favorites
        const container = document.getElementById('favorites-list');  // Define constant: container
        if(!container) return;  // Conditional guard/check before executing the next block
        container.innerHTML = '';  
        shiftFavorites.forEach((fav, index) => {  // Iterate over array elements
            const div = document.createElement('div');  // Define constant: div
            div.className = 'favorite-item';  
            div.draggable = true;  
            div.ondragstart = (ev) => favoriteDragStart(ev, index);  
            const label = `${decimalToDisplay(fav.start)} - ${decimalToDisplay(fav.end)}`;  // Define constant: label
            const duration = (fav.end - fav.start) - fav.break;  // Define constant: duration
            const sub = `${duration.toFixed(2)} Hrs`;  // Define constant: sub
            div.innerHTML = `  
                <div class="fav-info"><span>${label}</span><span class="fav-sub">${sub}</span></div>
                <button class="btn-delete" style="float:none;" onclick="removeFavorite(${index})">×</button>
            `;  // End of template literal (HTML snippet) used for UI rendering
            container.appendChild(div);  // Append a child node into the DOM
        });   
    }   
    function removeFavorite(index) { shiftFavorites.splice(index, 1); saveState(); renderFavorites(); }  // Remove/delete: remove favorite
    function favoritesDragOver(ev) { ev.preventDefault(); ev.currentTarget.classList.add('drag-over'); }  // Define function: favorites drag over
    function favoritesDragLeave(ev) { ev.currentTarget.classList.remove('drag-over'); }  // Define function: favorites drag leave
    function favoritesDropHandler(ev) {  // Define function: favorites drop handler
        ev.preventDefault(); ev.currentTarget.classList.remove('drag-over');  // Remove a CSS class to revert UI state/styling
        const type = ev.dataTransfer.getData("dragType");  // Define constant: type
        if(type === "shift_config") {  // Conditional guard/check before executing the next block
            const sHour = parseInt(document.getElementById('start-hour').value);  // Define constant: s hour
            const sMin = parseInt(document.getElementById('start-min').value);  // Define constant: s min
            const eHour = parseInt(document.getElementById('end-hour').value);  // Define constant: e hour
            const eMin = parseInt(document.getElementById('end-min').value);  // Define constant: e min
            const breakDur = 0;   // Define constant: break dur
            const startDec = sHour + (sMin / 60); const endDec = eHour + (eMin / 60);  // Define constant: start dec
            if (endDec <= startDec) { showMessage("Invalid shift times.", "error"); return; }  // Conditional guard/check before executing the next block
            shiftFavorites.push({ start: startDec, end: endDec, break: breakDur });  // Append a new item to an array (update scheduler data)
            saveState(); renderFavorites();  
        }   
    }   

// --- DRAG HANDLERS ---
    function staffDragStart(ev, empId) { ev.dataTransfer.setData("dragType", "staff"); ev.dataTransfer.setData("empId", empId); }  // Define function: staff drag start
    function shiftDragStart(ev) { ev.dataTransfer.setData("dragType", "shift_config"); }  // Define function: shift drag start
    function favoriteDragStart(ev, index) { ev.dataTransfer.setData("dragType", "favorite_shift"); ev.dataTransfer.setData("favIndex", index); }  // Define function: favorite drag start
function shiftCardDragStart(ev, shiftId) {
        const shift = schedule.find(s => s.id === shiftId);
        if(!shift) return;
        ev.dataTransfer.setData("dragType", "existing_shift");
        ev.dataTransfer.setData("start", shift.start);
        ev.dataTransfer.setData("end", shift.end);
        ev.dataTransfer.setData("break", shift.breakDuration);
        ev.dataTransfer.setData("isHoliday", shift.isHoliday || false);
        ev.dataTransfer.setData("isJobOnly", shift.isJobOnly || false);
        if(shift.lunchStart) ev.dataTransfer.setData("lunchStart", shift.lunchStart);
        if(shift.job) ev.dataTransfer.setData("job", shift.job);
        ev.stopPropagation();
    } 
    function duplicateDragStart(ev, empId, sourceWeekStart) { ev.dataTransfer.setData("dragType", "duplicate_schedule"); ev.dataTransfer.setData("empId", empId); ev.dataTransfer.setData("sourceWeek", sourceWeekStart); }  // Define function: duplicate drag start
    function rosterDragOver(ev) { ev.preventDefault(); ev.currentTarget.classList.add('drag-over'); }  // Define function: roster drag over
    function rosterDragLeave(ev) { ev.currentTarget.classList.remove('drag-over'); }  // Define function: roster drag leave
    function rosterDropHandler(ev, targetWeekStart) {  // Define function: roster drop handler
        ev.preventDefault(); ev.currentTarget.classList.remove('drag-over');  // Remove a CSS class to revert UI state/styling
        const dragType = ev.dataTransfer.getData("dragType");  // Define constant: drag type
        if (dragType === "staff") { openConfigModal(parseInt(ev.dataTransfer.getData("empId")), targetWeekStart); }  // Conditional guard/check before executing the next block
        else if (dragType === "duplicate_schedule") { duplicateSchedule(parseInt(ev.dataTransfer.getData("empId")), ev.dataTransfer.getData("sourceWeek"), targetWeekStart); }  // Alternative conditional branch
    }   
    function shiftDragOver(ev) { ev.preventDefault(); ev.currentTarget.classList.add('cell-drag-over'); }  // Define function: shift drag over
    function shiftDragLeave(ev) { ev.currentTarget.classList.remove('cell-drag-over'); }  // Define function: shift drag leave

   function shiftDropHandler(ev, empId, dateString, weekStartStr) {
        ev.preventDefault(); ev.currentTarget.classList.remove('cell-drag-over');
        const type = ev.dataTransfer.getData("dragType");
        
        if (type === "shift_config") { 
            createShift(empId, dateString, weekStartStr); 
        }
        else if (type === "favorite_shift") {
            const idx = parseInt(ev.dataTransfer.getData("favIndex"));
            const fav = shiftFavorites[idx];
            if(fav) createShift(empId, dateString, weekStartStr, fav);
        }
        else if (type === "existing_shift") {
            const lData = ev.dataTransfer.getData("lunchStart");
            const jobData = ev.dataTransfer.getData("job");
            const holidayData = ev.dataTransfer.getData("isHoliday") === "true";
            const isJobOnlyData = ev.dataTransfer.getData("isJobOnly") === "true";
            const data = {
                start: parseFloat(ev.dataTransfer.getData("start")),
                end: parseFloat(ev.dataTransfer.getData("end")),
                break: parseFloat(ev.dataTransfer.getData("break")),
                lunchStart: (lData && lData !== "null") ? parseFloat(lData) : null,
                job: (jobData && jobData !== "undefined") ? jobData : null,
                isHoliday: holidayData,
                isJobOnly: isJobOnlyData
            };
            createShift(empId, dateString, weekStartStr, data);
        }
        else if (type === "assign_job") {
            const jobName = ev.dataTransfer.getData("jobName");
            const data = {
                start: 9, 
                end: 9, 
                break: 0, 
                job: jobName, 
                isJobOnly: true 
            };
            createShift(empId, dateString, weekStartStr, data);
        }
    }

// --- SHIFT LOGIC ---
function createShift(empId, dateStr, weekStartStr, override = null) {
        const rosterEntry = weeklyRoster.find(r => r.empId === empId && r.weekStart === weekStartStr);
        if(!rosterEntry) return;

        let startDec, endDec, breakDur, lunchStart = null, job = null, isHoliday = false, isJobOnly = false;

        if (override) {
            startDec = override.start;
            endDec = override.end;
            breakDur = override.break;
            lunchStart = override.lunchStart || null;
            job = override.job || null;
            isHoliday = override.isHoliday || false;
            isJobOnly = override.isJobOnly || false;
        } else {
            const sHour = parseInt(document.getElementById('start-hour').value);
            const sMin = parseInt(document.getElementById('start-min').value);
            const eHour = parseInt(document.getElementById('end-hour').value);
            const eMin = parseInt(document.getElementById('end-min').value);
            breakDur = 0;
            lunchStart = null;
            job = currentConfigJob;
            startDec = sHour + (sMin / 60);
            endDec = eHour + (eMin / 60);
            isHoliday = false; 
            isJobOnly = false;
        }

        // --- NEW: Validation Update ---
        // Allow start == end ONLY if it is a Job Only shift
        if (!isJobOnly && endDec <= startDec) { 
            showMessage("End time must be after start.", "error"); return; 
        }
        // ------------------------------
        
        if (breakDur > 0) {
            if (lunchStart === null && !override) {
                    lunchStart = startDec + ((endDec - startDec) / 2) - (breakDur/2);
            }
            if (lunchStart !== null && (lunchStart < startDec || (lunchStart + breakDur) > endDec)) {
                showMessage("Lunch must be within shift hours.", "error"); return;
            }
        }

        schedule = schedule.filter(s => !(s.empId === empId && s.dateString === dateStr));
        
        // Check for clopens (late previous shift) - skip check for job only
        if (!isJobOnly) {
            const prevDate = new Date(dateStr + "T00:00:00"); prevDate.setDate(prevDate.getDate() - 1);
            const prevDateStr = formatDateString(prevDate);
            const lateShift = schedule.find(s => s.empId === empId && s.dateString === prevDateStr && s.end >= 22);
            if (lateShift && startDec <= 8) { if(!confirm(`CLOPEN WARNING: Worked late prev shift. Proceed?`)) return; }
        }

        const newShift = {
            id: Date.now(),
            empId,
            dateString: dateStr,
            start: startDec,
            end: endDec,
            breakDuration: breakDur,
            lunchStart: lunchStart,
            isHoliday: isHoliday,
            isJobOnly: isJobOnly,
            job: job // Ensure job is saved
        };

        if(job) newShift.job = job;
        schedule.push(newShift);
        saveState(); renderAll();
    }

    function pasteSchedule(targetEmpId, targetWeekStart) {  // Define function: paste schedule
        if (!clipboardSchedule) return;  // Conditional guard/check before executing the next block
        if(!confirm("Paste schedule? This will OVERWRITE their current shifts for this week.")) return;  // Conditional guard/check before executing the next block
        const targetDate = new Date(targetWeekStart + "T00:00:00");  // Define constant: target date
        const targetWeekDates = [];  // Define constant: target week dates
        for(let i=0; i<7; i++) {  // Loop over a range/collection to process items
            const d = new Date(targetDate);  // Define constant: d
            d.setDate(d.getDate() + i);  // Read/update Date components for week/day computations
            targetWeekDates.push(formatDateString(d));  // Append a new item to an array (update scheduler data)
        }   
        schedule = schedule.filter(s => {  // Create a filtered copy of an array based on a predicate
            const isTargetEmp = s.empId === targetEmpId;  // Define constant: is target emp
            const isInWeek = targetWeekDates.includes(s.dateString);  // Define constant: is in week
            return !(isTargetEmp && isInWeek);  // Return a value/exit point for this function
        });   
        let count = 0;  // Define state variable: count
        clipboardSchedule.shifts.forEach(src => {  // Iterate over array elements
            const newDate = new Date(targetDate);  // Define constant: new date
            newDate.setDate(newDate.getDate() + src.dayIndex);  // Read/update Date components for week/day computations
            const newDateStr = formatDateString(newDate);  // Define constant: new date str
            const newShift = {   // Define constant: new shift
                id: Date.now() + Math.random(),   
                empId: targetEmpId,   
                dateString: newDateStr,   
                start: src.start,   
                end: src.end,   
                breakDuration: src.breakDuration,   
                lunchStart: src.lunchStart   
            };   
            if(src.job) newShift.job = src.job;   // Conditional guard/check before executing the next block
            schedule.push(newShift);  // Append a new item to an array (update scheduler data)
            count++;  
        });   
        saveState();  
        clipboardSchedule = null;  
        renderAll();  
        showMessage(`Pasted schedule (Overwrote previous).`, "success");  
    }   

    function duplicateSchedule(empId, sourceWeek, targetWeek) {  // Define function: duplicate schedule
        if (sourceWeek === targetWeek) return;   // Conditional guard/check before executing the next block
        let targetRoster = weeklyRoster.find(r => r.empId === empId && r.weekStart === targetWeek);  // Define state variable: target roster
        if (!targetRoster) {  // Conditional guard/check before executing the next block
            const sourceRoster = weeklyRoster.find(r => r.empId === empId && r.weekStart === sourceWeek);  // Define constant: source roster
            if (sourceRoster) {  // Conditional guard/check before executing the next block
                weeklyRoster.push({ uniqueId: Date.now().toString(), empId: empId, weekStart: targetWeek, maxHours: sourceRoster.maxHours, blackoutDays: [...sourceRoster.blackoutDays] });  // Append a new item to an array (update scheduler data)
            } else { return; }   
        }   
        const sDate = new Date(sourceWeek + "T00:00:00");  // Define constant: s date
        const diffTime = new Date(targetWeek + "T00:00:00").getTime() - sDate.getTime();  // Define constant: diff time
        const sourceShifts = schedule.filter(s => {  // Define constant: source shifts
            if(s.empId !== empId) return false;  // Conditional guard/check before executing the next block
            const d = new Date(s.dateString + "T00:00:00");  // Define constant: d
            const day = d.getDay();   // Define constant: day
            const diff = day === 0 ? -6 : 1 - day;  // Define constant: diff
            const mon = new Date(d); mon.setDate(d.getDate() + diff);  // Define constant: mon
            return formatDateString(mon) === sourceWeek;  // Return a value/exit point for this function
        });   
        let count = 0;  // Define state variable: count
        sourceShifts.forEach(src => {  // Iterate over array elements
            const newD = new Date(new Date(src.dateString + "T00:00:00").getTime() + diffTime);  // Define constant: new d
            const newDateStr = formatDateString(newD);  // Define constant: new date str
            const exists = schedule.find(s => s.empId === empId && s.dateString === newDateStr && s.start === src.start && s.end === src.end);  // Define constant: exists
            if (!exists) {  // Conditional guard/check before executing the next block
                const newShift = {   // Define constant: new shift
                    id: Date.now() + Math.random(),   
                    empId,   
                    dateString: newDateStr,   
                    start: src.start,   
                    end: src.end,   
                    breakDuration: src.breakDuration,   
                    lunchStart: src.lunchStart   
                };   
                if(src.job) newShift.job = src.job;  // Conditional guard/check before executing the next block
                schedule.push(newShift);  // Append a new item to an array (update scheduler data)
                count++;  
            }   
        });   
        saveState(); showMessage(`Copied ${count} shifts.`, 'success'); renderAll();  
    }   

// --- MODAL ACTIONS ---
    function saveRosterConfig() {  // Save/persist data: roster config
        if(!pendingEmpId || !pendingWeekStart) return;  // Conditional guard/check before executing the next block
        const maxHours = parseInt(document.getElementById('modal-max-hours').value);  // Define constant: max hours
        if(maxHours > 40) { alert("Max limit cannot exceed 40 hours."); return; }  // Conditional guard/check before executing the next block
        const blackoutDays = Array.from(document.querySelectorAll('input[name="blackout"]:checked')).map(cb => cb.value);  // Define constant: blackout days
        if (pendingRosterUniqueId) {  // Conditional guard/check before executing the next block
            const entry = weeklyRoster.find(r => r.uniqueId === pendingRosterUniqueId);  // Define constant: entry
            if(entry) {  // Conditional guard/check before executing the next block
                entry.maxHours = maxHours;  
                entry.blackoutDays = blackoutDays;  
            }   
        } else {   
            weeklyRoster.push({   // Append a new item to an array (update scheduler data)
                uniqueId: Date.now().toString(),   
                empId: pendingEmpId,   
                weekStart: pendingWeekStart,   
                maxHours,   
                blackoutDays   
            });   
        }   
        if (blackoutDays.length > 0) {  // Conditional guard/check before executing the next block
            const weekDate = new Date(pendingWeekStart + "T00:00:00");  // Define constant: week date
            const forbiddenDates = [];  // Define constant: forbidden dates
            for(let i=0; i<7; i++) {  // Loop over a range/collection to process items
                const d = new Date(weekDate);  // Define constant: d
                d.setDate(d.getDate() + i);  // Read/update Date components for week/day computations
                const dayName = WEEKDAYS[d.getDay()];   // Define constant: day name
                if (blackoutDays.includes(dayName)) {  // Conditional guard/check before executing the next block
                    forbiddenDates.push(formatDateString(d));  // Loop over a range/collection to process items
                }   
            }   
            schedule = schedule.filter(s => {  // Create a filtered copy of an array based on a predicate
                const isTargetEmp = s.empId === pendingEmpId;  // Define constant: is target emp
                const isForbiddenDay = forbiddenDates.includes(s.dateString);  // Define constant: is forbidden day
                return !(isTargetEmp && isForbiddenDay);  // Return a value/exit point for this function
            });   
        }   
        saveState();   
        closeModal();   
        renderAll();   
    }   

    function closeModal() {   // Close UI modal/feature: modal
        document.getElementById('config-modal').close();   // Lookup DOM element by id: #config-modal
        pendingEmpId = null;   
        pendingWeekStart = null;   
        pendingRosterUniqueId = null;   
    }   

    function openConfigModal(empId, weekStart) {  // Open UI modal/feature: config modal
        const emp = staffPool.find(e => e.id === empId);  // Define constant: emp
        pendingRosterUniqueId = null;  
        if(!emp) return;  // Conditional guard/check before executing the next block
        const exists = weeklyRoster.find(r => r.empId === empId && r.weekStart === weekStart);  // Define constant: exists
        if(exists) { showMessage("Employee already in this week's roster.", "error"); return; }  // Conditional guard/check before executing the next block
        pendingEmpId = empId; pendingWeekStart = weekStart;  
        document.getElementById('modal-emp-name').innerText = `Configure ${emp.name}`;  // Lookup DOM element by id: #modal-emp-name
        document.getElementById('modal-week-date').innerText = weekStart;  // Lookup DOM element by id: #modal-week-date
        document.getElementById('modal-max-hours').value = 40;  // Lookup DOM element by id: #modal-max-hours
        document.querySelectorAll('input[name="blackout"]').forEach(cb => cb.checked = false);  // Iterate over array elements
        document.getElementById('config-modal').showModal();  // Lookup DOM element by id: #config-modal
    }   

function openLunchModal(shiftId) {
        const shift = schedule.find(s => s.id === shiftId);
        if (!shift) return;
        const emp = staffPool.find(e => e.id === shift.empId);
        pendingLunchShiftId = shiftId;
        
        document.getElementById('lunch-emp-name').innerText = emp ? emp.name : 'Staff';
        
        // --- NEW: Load Holiday Checkbox ---
        const holidayCb = document.getElementById('modal-shift-holiday');
        if(holidayCb) holidayCb.checked = shift.isHoliday || false;
        // ----------------------------------

        const jobSelect = document.getElementById('modal-shift-job');
        jobSelect.innerHTML = '<option value="">(None)</option>';
        jobList.forEach(job => {
            const opt = document.createElement('option');
            opt.value = job;
            opt.innerText = job;
            if (shift.job === job) opt.selected = true;
            jobSelect.appendChild(opt);
        });
        
        document.getElementById('modal-lunch-duration').value = shift.breakDuration || 0;
        
        if (shift.lunchStart) {
            const h = Math.floor(shift.lunchStart);
            const mDecimal = shift.lunchStart - h;
            const m = Math.round(mDecimal * 60);
            let roundedM = Math.round(m / 5) * 5;
            if (roundedM === 60) roundedM = 55;
            let mStr = roundedM.toString().padStart(2, '0');

            document.getElementById('modal-lunch-hour').value = h;
            document.getElementById('modal-lunch-min').value = mStr;
        } else {
            const defaultLunch = Math.floor(shift.start + 4);
            document.getElementById('modal-lunch-hour').value = defaultLunch > 19 ? 12 : defaultLunch;
            document.getElementById('modal-lunch-min').value = "00";
        }
        document.getElementById('lunch-modal').showModal();
    }

document.getElementById('btn-save-lunch').onclick = function() {
        if (!pendingLunchShiftId) return;
        
        // --- NEW: Read Holiday Checkbox ---
        const isHoliday = document.getElementById('modal-shift-holiday').checked;
        // ----------------------------------

        const dur = parseFloat(document.getElementById('modal-lunch-duration').value);
        let start = null;
        if (dur > 0) {
            const h = parseInt(document.getElementById('modal-lunch-hour').value);
            const m = parseInt(document.getElementById('modal-lunch-min').value);
            start = h + (m / 60);
        }
        
        const jobVal = document.getElementById('modal-shift-job').value;
        const shiftIdx = schedule.findIndex(s => s.id === pendingLunchShiftId);
        
        if (shiftIdx !== -1) {
            const s = schedule[shiftIdx];
            if (dur > 0 && (start < s.start || (start + dur) > s.end)) {
                alert("Lunch is outside shift hours!"); return;
            }
            
            schedule[shiftIdx].breakDuration = dur;
            schedule[shiftIdx].lunchStart = start;
            
            // --- NEW: Save Holiday Status ---
            schedule[shiftIdx].isHoliday = isHoliday;
            // --------------------------------

            if(jobVal) schedule[shiftIdx].job = jobVal;
            else delete schedule[shiftIdx].job;
            
            saveState();
            renderAll();
            showMessage("Shift Updated", "success");
        }
        document.getElementById('lunch-modal').close(); pendingLunchShiftId = null;
    }; 

// --- GLOBAL UTILS ---
    function removeRosterEntry(uniqueId) {  // Remove/delete: remove roster entry
        if(!confirm("Remove from this week? (This will clear their shifts for this week)")) return;  // Conditional guard/check before executing the next block
        const entry = weeklyRoster.find(r => r.uniqueId === uniqueId);  // Define constant: entry
        if (entry) {  // Conditional guard/check before executing the next block
            const weekDates = [];  // Define constant: week dates
            let currentDay = new Date(entry.weekStart + "T00:00:00");   // Define state variable: current day
            for(let i=0; i<7; i++) {  // Loop over a range/collection to process items
                weekDates.push(formatDateString(currentDay));  // Append a new item to an array (update scheduler data)
                currentDay.setDate(currentDay.getDate() + 1);  // Read/update Date components for week/day computations
            }   
            schedule = schedule.filter(s => {  // Create a filtered copy of an array based on a predicate
                const isTargetEmp = s.empId === entry.empId;  // Define constant: is target emp
                const isTargetWeek = weekDates.includes(s.dateString);  // Define constant: is target week
                return !(isTargetEmp && isTargetWeek);  // Return a value/exit point for this function
            });   
            weeklyRoster = weeklyRoster.filter(r => r.uniqueId !== uniqueId);  // Create a filtered copy of an array based on a predicate
            saveState();  
            renderAll();  
        }   
    }   

    function deleteShift(id) {   // Remove/delete: delete shift
        if(!confirm("Delete this shift?")) return;  // Conditional guard/check before executing the next block
        schedule = schedule.filter(s => s.id !== id);   // Create a filtered copy of an array based on a predicate
        saveState(); renderAll();   
    }   

    function decimalToDisplay(decimal) {  // Define function: decimal to display
        const hours = Math.floor(decimal); const minutes = Math.round((decimal - hours) * 60);  // Define constant: hours
        const ampm = hours >= 12 && hours < 24 ? 'PM' : 'AM'; let dh = hours % 12; if (dh === 0) dh = 12;  // Define constant: ampm
        const minStr = minutes < 10 ? '0' + minutes : minutes;  // Define constant: min str
        return `${dh}:${minStr} ${ampm}`;  // Return a value/exit point for this function
    }   
    function formatDateString(d) { return d.toISOString().split('T')[0]; }  // Format value for display/storage: date string
    function getDayName(d) { return WEEKDAYS[d.getDay()]; }  // Define function: get day name
    
    function populateTimeSelects() {  // Populate UI controls: time selects
        const fill = (hId, mId) => {  // Define constant: fill
            const hSel = document.getElementById(hId); const mSel = document.getElementById(mId);  // Define constant: h sel
            if(!hSel || !mSel) return;  // Conditional guard/check before executing the next block
            hSel.innerHTML = ''; mSel.innerHTML = '';  
            for (let h = 7; h <= 19; h++) {  // Loop over a range/collection to process items
                const ampm = h >= 12 ? 'PM' : 'AM'; let dispH = h % 12; if (dispH === 0) dispH = 12;  // Define constant: ampm
                hSel.add(new Option(`${dispH} ${ampm}`, h));  
            }   
            for (let m = 0; m < 60; m += 5) {
    const mStr = m < 10 ? '0' + m : m.toString();
    mSel.add(new Option(`:${mStr}`, mStr));
}
        };   
        fill('start-hour', 'start-min');  
        fill('end-hour', 'end-min');  
        fill('modal-lunch-hour', 'modal-lunch-min');  
        document.getElementById('start-hour').value = 9;  // Lookup DOM element by id: #start-hour
        document.getElementById('end-hour').value = 17;  // Lookup DOM element by id: #end-hour
    }   

    function showMessage(text, type) {  // Define function: show message
        const box = document.getElementById('message-box');   // Define constant: box
        if(!box) { alert(text); return; }  // Conditional guard/check before executing the next block
        box.innerText = text;   // Set text content for a DOM element
        box.className = type === 'error' ? 'msg-error' : 'msg-success';  
        box.style.display = 'block';   // Set inline styles to reflect UI state (e.g., drag-over, warnings)
        setTimeout(() => { box.style.display = 'none'; }, 4000);  // Set inline styles to reflect UI state (e.g., drag-over, warnings)
    }   

    function editDayNote(dateStr) {  // Define function: edit day note
        const current = dailyNotes[dateStr] || "";  // Define constant: current
        const note = prompt("Enter note for this day:", current);  // Define constant: note
        if (note !== null) {  // Conditional guard/check before executing the next block
            if(note.trim() === "") delete dailyNotes[dateStr];  // Conditional guard/check before executing the next block
            else dailyNotes[dateStr] = note;   
            saveState(); renderAll();  
        }   
    }   

// --- JOB LOGIC ---
    function renderJobList() {  // Render UI for: job list
        const container = document.getElementById('job-list');  // Define constant: container
        if(!container) return;  // Conditional guard/check before executing the next block
        container.innerHTML = '';  
        jobList.forEach((job, index) => {  // Iterate over array elements
            const div = document.createElement('div');  // Define constant: div
            div.className = 'job-pill';  
            div.draggable = true;  
            div.ondragstart = (ev) => {  // Begin block scope
                ev.dataTransfer.effectAllowed = "copy";  // Use Drag-and-Drop dataTransfer payload
                ev.dataTransfer.setData("dragType", "assign_job");  // Use Drag-and-Drop dataTransfer payload
                ev.dataTransfer.setData("jobName", job);  // Use Drag-and-Drop dataTransfer payload
            };   
            div.innerHTML = `<span>${escapeHTML(job)}</span> <button class="btn-delete" style="float:none" onclick="removeJob(${index})">×</button>`;  
            container.appendChild(div);  // Append a child node into the DOM
        });   
    }   

    function addJob() {  // Add/create: job
        const input = document.getElementById('new-job-name');  // Define constant: input
        const name = input.value.trim();  // Define constant: name
        if (!name) return;  // Conditional guard/check before executing the next block
        jobList.push(name);  // Append a new item to an array (update scheduler data)
        input.value = '';  
        saveState();  
        renderJobList();  
    }   

    function removeJob(index) {  // Remove/delete: remove job
        if(!confirm("Remove this job type?")) return;  // Conditional guard/check before executing the next block
        jobList.splice(index, 1);  // Remove/replace items within an array (update scheduler data)
        saveState();  
        renderJobList();  
    }   

    function handleJobDrop(ev, shiftId) {  // Define function: handle job drop
        ev.preventDefault();  
        const type = ev.dataTransfer.getData("dragType");  // Define constant: type
        if (type === "assign_job") {  // Conditional guard/check before executing the next block
            ev.stopPropagation();   
            const jobName = ev.dataTransfer.getData("jobName");  // Define constant: job name
            const shift = schedule.find(s => s.id === shiftId);  // Define constant: shift
            if (shift) {  // Conditional guard/check before executing the next block
                shift.job = jobName;  
                saveState();  
                renderAll();  
            }   
        }   
    }   

    function removeJobFromShift(shiftId, ev) {  // Remove/delete: remove job from shift
        ev.stopPropagation();   
        const shift = schedule.find(s => s.id === shiftId);  // Define constant: shift
        if(shift) {  // Conditional guard/check before executing the next block
            delete shift.job;  
            saveState();  
            renderAll();  
        }   
    }   

    function changeDate(offset) {  // Define function: change date
        const picker = document.getElementById('start-date-picker');  // Define constant: picker
        if(!picker.value) return;  // Conditional guard/check before executing the next block
        const d = new Date(picker.valueAsDate);  // Define constant: d
        const utcDate = new Date(Date.UTC(d.getUTCFullYear(), d.getUTCMonth(), d.getUTCDate()));  // Define constant: utc date
        if (currentView === 'monthly') {  // Conditional guard/check before executing the next block
            utcDate.setUTCMonth(utcDate.getUTCMonth() + offset);  
        }    
        else if (currentView === 'weekly' || currentView === 'tasks') {  // Alternative conditional branch
            utcDate.setUTCDate(utcDate.getUTCDate() + (offset * 7));  
        }    
        else {   
            utcDate.setUTCDate(utcDate.getUTCDate() + offset);  
            while (utcDate.getUTCDay() === 0) {  // Loop while condition remains true
                utcDate.setUTCDate(utcDate.getUTCDate() + (offset > 0 ? 1 : -1));  
            }   
        }   
        if ((currentView === 'weekly' || currentView === 'tasks') && utcDate.getUTCDay() === 0) {  // Conditional guard/check before executing the next block
            utcDate.setUTCDate(utcDate.getUTCDate() + 1);  
        }   
        picker.valueAsDate = utcDate;  
        renderAll();  
    }   

// --- TASKS VIEW LOGIC ---
    function renderTasksView() {  // Render UI for: tasks view
        const container = document.getElementById('schedule-container');  // Define constant: container
        container.innerHTML = '';  
        const btnBar = document.createElement('div');  // Define constant: btn bar
        btnBar.style.marginBottom = "15px";  // Set inline styles to reflect UI state (e.g., drag-over, warnings)
        btnBar.innerHTML = `<button class="primary" onclick="openTaskModal()">Manage Tasks</button>`;  
        container.appendChild(btnBar);  // Append a child node into the DOM

        const startDateInput = document.getElementById('start-date-picker').value;  // Define constant: start date input
        if(!startDateInput) return;  // Conditional guard/check before executing the next block
        const parts = startDateInput.split('-');  // Define constant: parts
        const year = parseInt(parts[0]);  // Define constant: year
        const month = parseInt(parts[1]) - 1;  // Define constant: month
        const dayNum = parseInt(parts[2]);  // Define constant: day num
        const d = new Date(year, month, dayNum);  // Define constant: d
        const day = d.getDay();  // Define constant: day
        const diff = d.getDate() - day + (day === 0 ? -6 : 1);  // Define constant: diff
        const monday = new Date(d);  // Define constant: monday
        monday.setDate(diff);  // Read/update Date components for week/day computations
        const weekDates = [];  // Define constant: week dates
        for(let i=0; i<5; i++) {  // Loop over a range/collection to process items
            weekDates.push(new Date(monday));  // Append a new item to an array (update scheduler data)
            monday.setDate(monday.getDate() + 1);  // Read/update Date components for week/day computations
        }   

        // Legacy key migration support (old keys were date + cleaned task name).
        // We keep reading legacy keys, but new assignments use a collision-resistant key.
        const legacyTaskNameCounts = {};  // Define constant: legacy task name counts
        for (const tasks of Object.values(tasksData)) {  // Loop over a range/collection to process items
            if (!Array.isArray(tasks)) continue;  // Conditional guard/check before executing the next block
            tasks.forEach(t => {  // Iterate over array elements
                const clean = String(t || '').replace(/[^a-zA-Z0-9]/g, '');  // Define constant: clean
                legacyTaskNameCounts[clean] = (legacyTaskNameCounts[clean] || 0) + 1;  
            });   
        }   
        let migrated = false;  // Define state variable: migrated

        let html = `<table><thead><tr><th class="task-name-cell">Job Name</th>`;  // Define state variable: html
        weekDates.forEach(date => {  // Iterate over array elements
            const dateStr = (date.getMonth()+1) + '/' + date.getDate();  // Define constant: date str
            const dayName = getDayName(date).substring(0,3);  // Define constant: day name
            html += `<th>${dayName} ${dateStr}</th>`;  
        });   
        html += `</tr></thead><tbody>`;  

        for (const [category, tasks] of Object.entries(tasksData)) {  // Loop over a range/collection to process items
            html += `<tr><td colspan="6" class="task-category-header">${escapeHTML(category)}</td></tr>`;  
            tasks.forEach(task => {  // Iterate over array elements
                html += `<tr>`;  
                html += `<td class="task-name-cell">${escapeHTML(task)}</td>`;  
                weekDates.forEach(date => {  // Iterate over array elements
                    const dateKey = formatDateString(date);  // Define constant: date key
                    const cleanTaskName = task.replace(/[^a-zA-Z0-9]/g, '');  // Define constant: clean task name
                    const legacyKey = `${dateKey}_${cleanTaskName}`;  // Define constant: legacy key
                    const uniqueKey = buildTaskAssignmentKey(dateKey, category, task);  // Define constant: unique key

                    let assignedId = taskAssignments[uniqueKey];  // Define state variable: assigned id

                    // Fallback to legacy key (and migrate when unambiguous)
                    if (!assignedId && taskAssignments[legacyKey]) {  // Conditional guard/check before executing the next block
                        assignedId = taskAssignments[legacyKey];  
                        const legacyCount = legacyTaskNameCounts[cleanTaskName] || 0;  // Define constant: legacy count
                        if (legacyCount === 1) {  // Conditional guard/check before executing the next block
                            taskAssignments[uniqueKey] = assignedId;  
                            delete taskAssignments[legacyKey];  
                            migrated = true;  
                        }   
                    }   
                    let cellContent = "";  // Define state variable: cell content
                    if (assignedId) {  // Conditional guard/check before executing the next block
                        const emp = staffPool.find(e => e.id === assignedId);  // Define constant: emp
                        if (emp) {  // Conditional guard/check before executing the next block
                            cellContent = `<div class="task-chip">  
                                ${escapeHTML(emp.name)} 
                                <span style="cursor:pointer; color:var(--danger);" onclick="removeTaskAssignment('${uniqueKey}', '${legacyKey}')">×</span>
                            </div>`;  // End of template literal (HTML snippet) used for UI rendering
                        }   
                    }   
                    html += `<td class="task-assign-cell"   
                                ondrop="taskDropHandler(event, '${uniqueKey}', '${legacyKey}')" 
                                ondragover="event.preventDefault(); this.classList.add('drag-over')" 
                                ondragleave="this.classList.remove('drag-over')">
                                ${cellContent}
                            </td>`;  // End of template literal (HTML snippet) used for UI rendering
                });   
                html += `</tr>`;  
            });   
        }   
        html += `</tbody></table>`;  
        if (migrated) {  // Conditional guard/check before executing the next block
            saveState();  
        }   

        const wrapper = document.createElement('div');  // Define constant: wrapper
        wrapper.className = 'week-container';  
        wrapper.innerHTML = html;  
        container.appendChild(wrapper);  // Append a child node into the DOM
    }   

    function taskDropHandler(ev, uniqueKey, legacyKey = null) {  // Define function: task drop handler
        ev.preventDefault();  
        ev.currentTarget.classList.remove('drag-over');  // Remove a CSS class to revert UI state/styling
        const type = ev.dataTransfer.getData("dragType");  // Define constant: type
        if (type === "staff") {  // Conditional guard/check before executing the next block
            const empId = parseInt(ev.dataTransfer.getData("empId"));  // Define constant: emp id
            taskAssignments[uniqueKey] = empId;  
            if (legacyKey && legacyKey !== uniqueKey && taskAssignments[legacyKey]) {  // Conditional guard/check before executing the next block
                delete taskAssignments[legacyKey];  
            }   
            saveState();  
            renderAll();   
        }   
    }   

    function removeTaskAssignment(uniqueKey, legacyKey = null) {  // Remove/delete: remove task assignment
        let changed = false;  // Define state variable: changed
        if (taskAssignments[uniqueKey]) {  // Conditional guard/check before executing the next block
            delete taskAssignments[uniqueKey];  
            changed = true;  
        }   
        if (legacyKey && taskAssignments[legacyKey]) {  // Conditional guard/check before executing the next block
            delete taskAssignments[legacyKey];  
            changed = true;  
        }   
        if (changed) {  // Conditional guard/check before executing the next block
            saveState();  
            renderAll();  
        }   
    }   

// --- TASK MANAGEMENT LOGIC ---
    function openTaskModal() {  // Open UI modal/feature: task modal
        renderTaskManagerList();  
        document.getElementById('task-modal').showModal();  // Lookup DOM element by id: #task-modal
    }   

    function renderTaskManagerList() {  // Render UI for: task manager list
        const list = document.getElementById('task-manager-list');  // Define constant: list
        const cat = document.getElementById('manage-task-cat').value;  // Define constant: cat
        list.innerHTML = '';  
        if (tasksData[cat]) {  // Conditional guard/check before executing the next block
            tasksData[cat].forEach((task, index) => {  // Iterate over array elements
                const div = document.createElement('div');  // Define constant: div
                div.className = 'job-pill';  
                div.style.background = 'white';   // Set inline styles to reflect UI state (e.g., drag-over, warnings)
                div.style.cursor = 'grab';  // Set inline styles to reflect UI state (e.g., drag-over, warnings)
                div.draggable = true;  
                div.ondragstart = (ev) => taskReorderDragStart(ev, index);  
                div.ondragover = (ev) => taskReorderDragOver(ev);  
                div.ondrop = (ev) => taskReorderDrop(ev, index);           
                div.ondragleave = (ev) => taskReorderDragLeave(ev);   
                div.innerHTML = `  
                    <span>${escapeHTML(task)}</span>
                    <button class="btn-delete" style="float:none" onclick="removeTaskFromList('${cat}', ${index})">×</button>
                `;  // End of template literal (HTML snippet) used for UI rendering
                list.appendChild(div);  // Append a child node into the DOM
            });   
        }   
    }   

    function addTaskFromModal() {  // Add/create: task from modal
        const cat = document.getElementById('manage-task-cat').value;  // Define constant: cat
        const input = document.getElementById('new-task-name');  // Define constant: input
        const name = input.value.trim();  // Define constant: name
        if (!name) return;  // Conditional guard/check before executing the next block
        if (!tasksData[cat]) tasksData[cat] = [];  // Conditional guard/check before executing the next block
        tasksData[cat].push(name);  // Append a new item to an array (update scheduler data)
        input.value = '';  
        saveState();  
        renderTaskManagerList();   
        renderTasksView();         
    }   

    function removeTaskFromList(cat, index) {  // Remove/delete: remove task from list
        if(!confirm("Delete this task?")) return;  // Conditional guard/check before executing the next block
        tasksData[cat].splice(index, 1);  // Remove/replace items within an array (update scheduler data)
        saveState();  
        renderTaskManagerList();  
        renderTasksView();  
    }   

    function taskReorderDragStart(ev, index) {  // Define function: task reorder drag start
        ev.dataTransfer.effectAllowed = "move";  // Use Drag-and-Drop dataTransfer payload
        ev.dataTransfer.setData("dragType", "reorder_task");  // Use Drag-and-Drop dataTransfer payload
        ev.dataTransfer.setData("srcIndex", index);  // Use Drag-and-Drop dataTransfer payload
        ev.target.style.opacity = '0.5';  // Set inline styles to reflect UI state (e.g., drag-over, warnings)
    }   

    function taskReorderDragOver(ev) {  // Define function: task reorder drag over
        ev.preventDefault();   
        ev.dataTransfer.dropEffect = "move";  // Use Drag-and-Drop dataTransfer payload
        ev.currentTarget.style.borderTop = "2px solid var(--primary)";  // Set inline styles to reflect UI state (e.g., drag-over, warnings)
    }   

    function taskReorderDrop(ev, targetIndex) {  // Define function: task reorder drop
        ev.preventDefault();  
        ev.stopPropagation();  
        ev.currentTarget.style.borderTop = "";  // Set inline styles to reflect UI state (e.g., drag-over, warnings)
        ev.currentTarget.style.opacity = '1';  // Set inline styles to reflect UI state (e.g., drag-over, warnings)
        const type = ev.dataTransfer.getData("dragType");  // Define constant: type
        if (type !== "reorder_task") return;  // Conditional guard/check before executing the next block
        const cat = document.getElementById('manage-task-cat').value;  // Define constant: cat
        const srcIndex = parseInt(ev.dataTransfer.getData("srcIndex"));  // Define constant: src index
        if (srcIndex === targetIndex) return;  // Conditional guard/check before executing the next block
        const list = tasksData[cat];  // Define constant: list
        const [movedItem] = list.splice(srcIndex, 1);  // Remove/replace items within an array (update scheduler data)
        list.splice(targetIndex, 0, movedItem);         // Remove/replace items within an array (update scheduler data)
        saveState();  
        renderTaskManagerList();   
        renderTasksView();  
    }   

    function taskReorderDragLeave(ev) {  // Define function: task reorder drag leave
        ev.currentTarget.style.borderTop = "";   // Set inline styles to reflect UI state (e.g., drag-over, warnings)
    }   

// --- SHARE CODE LOGIC ---
    async function openShareModal() {  // Begin block scope
        const data = {   // Define constant: data
            staffPool, weeklyRoster, schedule,   
            shiftFavorites, dailyNotes, jobList,   
            taskAssignments, tasksData  
        };   
        const textArea = document.getElementById('share-code-input');  // Define constant: text area
        textArea.value = "Generating compressed code...";  
        try {  // Begin error-handling block
            const jsonString = JSON.stringify(data);  // Define constant: json string
            const stream = new Blob([jsonString]).stream();  // Define constant: stream
            const compressedReadableStream = stream.pipeThrough(new CompressionStream("gzip"));  // Define constant: compressed readable stream
            const compressedResponse = new Response(compressedReadableStream);  // Define constant: compressed response
            const blob = await compressedResponse.blob();  // Define constant: blob
            const buffer = await blob.arrayBuffer();  // Define constant: buffer
            let binary = '';  // Define state variable: binary
            const bytes = new Uint8Array(buffer);  // Define constant: bytes
            const len = bytes.byteLength;  // Define constant: len
            for (let i = 0; i < len; i++) {  // Loop over a range/collection to process items
                binary += String.fromCharCode(bytes[i]);  
            }   
            const code = 'SCHME:' + btoa(binary);  // Define constant: code
            textArea.value = code;  
            textArea.select();   
            document.getElementById('share-modal').showModal();  // Lookup DOM element by id: #share-modal
        } catch (e) {  // Begin block scope
            console.error(e);  
            alert("Error generating code: " + e.message);  // Show an alert dialog to the user
            textArea.value = "";  
        }   
    }   

    function copyShareCode() {  // Define function: copy share code
        const textArea = document.getElementById('share-code-input');  // Define constant: text area
        textArea.select();  
        navigator.clipboard.writeText(textArea.value).then(() => {  // Use the browser Clipboard API (copy/paste)
            alert("Code copied to clipboard!");  // Show an alert dialog to the user
        }).catch(err => {  // Begin block scope
            alert("Failed to copy. Please manually select and copy.");  // Show an alert dialog to the user
        });   
    }   

    async function loadFromShareCode() {  // Begin block scope
        const rawInput = document.getElementById('share-code-input').value.trim();  // Define constant: raw input
        if (!rawInput) {  // Conditional guard/check before executing the next block
            alert("Please paste a code first.");  // Show an alert dialog to the user
            return;  // Return a value/exit point for this function
        }   
        if (!confirm("Loading this code will OVERWRITE your current schedule. Continue?")) return;  // Conditional guard/check before executing the next block
        try {  // Begin error-handling block
            let jsonString;  // Define state variable: json string
            if (rawInput.startsWith('SCHME:')) {  // Conditional guard/check before executing the next block
                const base64 = rawInput.substring(5);  // Define constant: base64
                const binary = atob(base64);  // Define constant: binary
                const bytes = new Uint8Array(binary.length);  // Define constant: bytes
                for (let i = 0; i < binary.length; i++) {  // Loop over a range/collection to process items
                    bytes[i] = binary.charCodeAt(i);  
                }   
                const stream = new Blob([bytes]).stream();  // Define constant: stream
                const decompressedStream = stream.pipeThrough(new DecompressionStream("gzip"));  // Define constant: decompressed stream
                const response = new Response(decompressedStream);  // Define constant: response
                jsonString = await response.text();  
            } else if (rawInput.startsWith('CBS1:')) {  // Alternative conditional branch
                const cleanCode = rawInput.substring(5);  // Define constant: clean code
                jsonString = decodeURIComponent(escape(atob(cleanCode)));  // Base64-decode into a binary/ASCII string
            } else {   
                jsonString = rawInput.startsWith('{') ? rawInput : decodeURIComponent(escape(atob(rawInput)));  // Base64-decode into a binary/ASCII string
            }   
            const data = JSON.parse(jsonString);  // Define constant: data
            if (data.weeklyRoster && data.schedule) {  // Conditional guard/check before executing the next block
                staffPool = data.staffPool || [];  
                weeklyRoster = data.weeklyRoster;  
                schedule = data.schedule;  
                shiftFavorites = data.shiftFavorites || [];  
                dailyNotes = data.dailyNotes || {};  
                jobList = data.jobList || [];  
                taskAssignments = data.taskAssignments || {};  
                if (data.tasksData) tasksData = data.tasksData;  // Conditional guard/check before executing the next block
                saveState();  
                renderStaffPool();     
                renderJobList();       
                renderFavorites();  
                renderAll();  
                document.getElementById('share-modal').close();  // Lookup DOM element by id: #share-modal
                showMessage("Schedule Loaded Successfully!", "success");  
            } else {   
                throw new Error("Missing roster/schedule data");  
            }   
        } catch (e) {  // Begin block scope
            alert("Invalid or Corrupt Share Code.");  // Show an alert dialog to the user
            console.error(e);  
        }   
    }   

    function copySchedule(empId, sourceWeek) {  // Define function: copy schedule
        const emp = staffPool.find(e => e.id === empId);  // Define constant: emp
        if (!emp) return;  // Conditional guard/check before executing the next block
        const sDate = new Date(sourceWeek + "T00:00:00");  // Define constant: s date
        const weekDates = [];  // Define constant: week dates
        for(let i=0; i<7; i++) {  // Loop over a range/collection to process items
            const d = new Date(sDate);  // Define constant: d
            d.setDate(d.getDate() + i);  // Read/update Date components for week/day computations
            weekDates.push(formatDateString(d));  // Append a new item to an array (update scheduler data)
        }   
        const shiftsToCopy = schedule.filter(s => s.empId === empId && weekDates.includes(s.dateString));  // Define constant: shifts to copy
        if (shiftsToCopy.length === 0) {  // Conditional guard/check before executing the next block
            showMessage("No shifts to copy.", "error");  
            return;  // Return a value/exit point for this function
        }   
        clipboardSchedule = {  // Begin block scope
            empId: empId,           
            empName: emp.name,      
            sourceWeek: sourceWeek,  
            shifts: shiftsToCopy.map(s => {  // Transform an array into a new array
                const shiftDate = new Date(s.dateString + "T00:00:00");  // Define constant: shift date
                const diffTime = shiftDate.getTime() - sDate.getTime();  // Define constant: diff time
                const dayIndex = Math.round(diffTime / (1000 * 3600 * 24));   // Define constant: day index
                return {  // Return a value/exit point for this function
                    dayIndex: dayIndex,  
                    start: s.start,  
                    end: s.end,  
                    breakDuration: s.breakDuration,  
                    lunchStart: s.lunchStart,  
                    job: s.job  
                };   
            })   
        };   
        renderAll();   
        showMessage(`Copied ${emp.name}'s schedule.`, "success");  
    }   

    function pasteScheduleToWeek(targetWeekStart) {  // Define function: paste schedule to week
        if (!clipboardSchedule) return;  // Conditional guard/check before executing the next block
        const targetEmpId = clipboardSchedule.empId;  // Define constant: target emp id
        const pastedName = clipboardSchedule.empName;   // Define constant: pasted name
        let rosterEntry = weeklyRoster.find(r => r.empId === targetEmpId && r.weekStart === targetWeekStart);  // Define state variable: roster entry
        if (!rosterEntry) {  // Conditional guard/check before executing the next block
            const srcRoster = weeklyRoster.find(r => r.empId === targetEmpId && r.weekStart === clipboardSchedule.sourceWeek);  // Define constant: src roster
            weeklyRoster.push({  // Append a new item to an array (update scheduler data)
                uniqueId: Date.now().toString(),  
                empId: targetEmpId,  
                weekStart: targetWeekStart,  
                maxHours: srcRoster ? srcRoster.maxHours : 40,  
                blackoutDays: srcRoster ? [...srcRoster.blackoutDays] : []  
            });   
        }   
        const targetDate = new Date(targetWeekStart + "T00:00:00");  // Define constant: target date
        let count = 0;  // Define state variable: count
        clipboardSchedule.shifts.forEach(src => {  // Iterate over array elements
            const newDate = new Date(targetDate);  // Define constant: new date
            newDate.setDate(newDate.getDate() + src.dayIndex);  // Read/update Date components for week/day computations
            const newDateStr = formatDateString(newDate);  // Define constant: new date str
            const exists = schedule.find(s => s.empId === targetEmpId && s.dateString === newDateStr && s.start === src.start);  // Define constant: exists
            if (!exists) {  // Conditional guard/check before executing the next block
                const newShift = {   // Define constant: new shift
                    id: Date.now() + Math.random(),   
                    empId: targetEmpId,   
                    dateString: newDateStr,   
                    start: src.start,   
                    end: src.end,   
                    breakDuration: src.breakDuration,   
                    lunchStart: src.lunchStart   
                };   
                if(src.job) newShift.job = src.job;  // Conditional guard/check before executing the next block
                schedule.push(newShift);  // Append a new item to an array (update scheduler data)
                count++;  
            }   
        });   
        saveState();  
        clipboardSchedule = null;   
        renderAll();  
        showMessage(`Added ${pastedName} and ${count} shifts.`, "success");  
    }   

// --- CONFIG PANEL JOB DROP LOGIC ---
    function configJobDragOver(ev) {  // Define function: config job drag over
        ev.preventDefault();   
        ev.dataTransfer.dropEffect = "copy";   // Use Drag-and-Drop dataTransfer payload
        const div = ev.currentTarget;  // Define constant: div
        div.style.borderColor = "var(--primary)";  // Set inline styles to reflect UI state (e.g., drag-over, warnings)
        div.style.background = "#eef2ff";   // Set inline styles to reflect UI state (e.g., drag-over, warnings)
        div.style.color = "var(--primary)";  // Set inline styles to reflect UI state (e.g., drag-over, warnings)
    }   

    function configJobDragLeave(ev) {  // Define function: config job drag leave
        if (ev.currentTarget.contains(ev.relatedTarget)) return;  // Conditional guard/check before executing the next block
        renderConfigJobDisplay();   
    }   

    function configJobDrop(ev) {  // Define function: config job drop
        ev.preventDefault();   
        ev.stopPropagation();   
        const type = ev.dataTransfer.getData("dragType");  // Define constant: type
        if (type === "assign_job") {  // Conditional guard/check before executing the next block
            currentConfigJob = ev.dataTransfer.getData("jobName");  // Use Drag-and-Drop dataTransfer payload
            renderConfigJobDisplay();  
        } else {   
            renderConfigJobDisplay();   
        }   
    }   

    function removeConfigJob() {  // Remove/delete: remove config job
        currentConfigJob = null;  
        renderConfigJobDisplay();  
    }   

    function renderConfigJobDisplay() {  // Render UI for: config job display
        const div = document.getElementById('config-job-display');  // Define constant: div
        if (!div) return;  // Conditional guard/check before executing the next block
        if (currentConfigJob) {  // Conditional guard/check before executing the next block
            div.style.borderStyle = "solid";  // Set inline styles to reflect UI state (e.g., drag-over, warnings)
            div.style.borderColor = "#6366f1";   // Set inline styles to reflect UI state (e.g., drag-over, warnings)
            div.style.background = "#eef2ff";    // Set inline styles to reflect UI state (e.g., drag-over, warnings)
            div.style.color = "#4338ca";         // Set inline styles to reflect UI state (e.g., drag-over, warnings)
            div.style.fontWeight = "bold";  // Set inline styles to reflect UI state (e.g., drag-over, warnings)
            div.innerHTML = `  
                <span>${escapeHTML(currentConfigJob)}</span> 
                <span onclick="removeConfigJob()" style="cursor:pointer; margin-left:10px; color:#ef4444; font-weight:bold; font-size:1.1em;">×</span>
            `;  // End of template literal (HTML snippet) used for UI rendering
        } else {   
            div.style.borderStyle = "dashed";  // Set inline styles to reflect UI state (e.g., drag-over, warnings)
            div.style.borderColor = "#cbd5e1";  // Set inline styles to reflect UI state (e.g., drag-over, warnings)
            div.style.background = "#f8fafc";  // Set inline styles to reflect UI state (e.g., drag-over, warnings)
            div.style.color = "#64748b";  // Set inline styles to reflect UI state (e.g., drag-over, warnings)
            div.style.fontWeight = "normal";  // Set inline styles to reflect UI state (e.g., drag-over, warnings)
            div.innerHTML = "Drag Job Here to Set Default";  
        }   
    }   

    function openRosterSettings(uniqueId) {  // Open UI modal/feature: roster settings
        const entry = weeklyRoster.find(r => r.uniqueId === uniqueId);  // Define constant: entry
        if(!entry) return;  // Conditional guard/check before executing the next block
        const emp = staffPool.find(e => e.id === entry.empId);  // Define constant: emp
        pendingEmpId = entry.empId;  
        pendingWeekStart = entry.weekStart;  
        pendingRosterUniqueId = uniqueId;   
        document.getElementById('modal-emp-name').innerText = `Edit Settings: ${emp.name}`;  // Lookup DOM element by id: #modal-emp-name
        document.getElementById('modal-week-date').innerText = entry.weekStart;  // Lookup DOM element by id: #modal-week-date
        document.getElementById('modal-max-hours').value = entry.maxHours;  // Lookup DOM element by id: #modal-max-hours
        document.querySelectorAll('input[name="blackout"]').forEach(cb => {  // Iterate over array elements
            cb.checked = entry.blackoutDays.includes(cb.value);  
        });   
        document.getElementById('config-modal').showModal();  // Lookup DOM element by id: #config-modal
    }   

// --- TASK KEY HELPERS ---
    function sanitizeKeyPart(str) {  // Define function: sanitize key part
        return String(str || '').replace(/[^a-zA-Z0-9]/g, '_');  // Return a value/exit point for this function
    }   

    // FNV-1a 32-bit hash (stable; prevents collisions better than "cleaned name")
    function hashString(str) {  // Define function: hash string
        let h = 0x811c9dc5;  // Define state variable: h
        const s = String(str || '');  // Define constant: s
        for (let i = 0; i < s.length; i++) {  // Loop over a range/collection to process items
            h ^= s.charCodeAt(i);  
            h = (h * 0x01000193) >>> 0;  
        }   
        return ('00000000' + h.toString(16)).slice(-8);  // Return a value/exit point for this function
    }   

    function buildTaskAssignmentKey(dateKey, category, taskName) {  // Define function: build task assignment key
        const safeDate = String(dateKey || '').replace(/[^0-9-]/g, '');  // Define constant: safe date
        const safeCat = sanitizeKeyPart(category);  // Define constant: safe cat
        const taskHash = hashString(taskName);  // Define constant: task hash
        return `${safeDate}_${safeCat}_${taskHash}`;  // Return a value/exit point for this function
    }   

// --- SECURITY: SANITIZE INPUTS ---
    function escapeHTML(str) {  // Define function: escape html
        if (!str) return str;  // Conditional guard/check before executing the next block
        return str  // Return a value/exit point for this function
            .replace(/&/g, "&amp;")  
            .replace(/</g, "&lt;")  
            .replace(/>/g, "&gt;")  
            .replace(/"/g, "&quot;")  
            .replace(/'/g, "&#039;");  
    }   

    // --- INIT CALL ---
    init();  
</script>
</body>
</html>

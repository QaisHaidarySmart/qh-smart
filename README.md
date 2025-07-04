<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>پروفایل حرفه‌ای | قیس حیدری</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <style>
        :root {
            --primary: #1a237e;
            --secondary: #311b92;
            --accent: #1a73e8;
            --earth: #4e342e;
            --light: #f8f9fa;
            --dark: #0d0a1f;
            --success: #4caf50;
            --error: #e53935;
            --warning: #ffb300;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Vazir', 'Segoe UI', Tahoma, sans-serif;
        }
        
        body {
            background-color: var(--light);
            color: var(--dark);
            line-height: 1.8;
            transition: all 0.3s ease;
        }
        
        .dark-theme {
            --light: #0d0a1f;
            --dark: #f8f9fa;
            --primary: #4fc3f7;
            --secondary: #1e88e5;
            --earth: #8d6e63;
            background: #121212;
        }
        
        .dark-theme .section {
            background: #1e1e1e;
            border-color: rgba(255, 255, 255, 0.05);
            box-shadow: 0 5px 25px rgba(0, 0, 0, 0.3);
        }
        
        .dark-theme .profile-nav {
            background: #252525;
        }
        
        /* Header Styles */
        .profile-header {
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            color: white;
            padding: 3rem 2rem;
            text-align: center;
            position: relative;
            overflow: hidden;
        }
        
        .header-pattern {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            opacity: 0.1;
            background-image: 
                radial-gradient(circle at 10% 20%, var(--accent) 0%, transparent 20%),
                radial-gradient(circle at 90% 80%, var(--success) 0%, transparent 25%);
        }
        
        .avatar-container {
            position: relative;
            width: 180px;
            height: 180px;
            margin: 0 auto 1.5rem;
            border-radius: 50%;
            border: 5px solid rgba(255, 255, 255, 0.3);
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
        }
        
        .avatar {
            width: 100%;
            height: 100%;
            background: linear-gradient(45deg, #4fc3f7, #1a237e);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 4rem;
            color: white;
            font-weight: bold;
        }
        
        .profile-title {
            font-size: 2.5rem;
            margin-bottom: 0.5rem;
            letter-spacing: 1px;
        }
        
        .profile-subtitle {
            font-size: 1.3rem;
            opacity: 0.9;
            margin-bottom: 1.5rem;
            font-weight: 300;
        }
        
        .badges-container {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin-top: 1rem;
            flex-wrap: wrap;
        }
        
        .badge {
            background: rgba(255, 255, 255, 0.15);
            backdrop-filter: blur(10px);
            border-radius: 50px;
            padding: 0.5rem 1.2rem;
            font-size: 0.9rem;
            display: flex;
            align-items: center;
            gap: 8px;
            border: 1px solid rgba(255, 255, 255, 0.2);
        }
        
        /* Navigation */
        .profile-nav {
            background: white;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
            position: sticky;
            top: 0;
            z-index: 100;
        }
        
        .nav-container {
            display: flex;
            justify-content: center;
            max-width: 1200px;
            margin: 0 auto;
            overflow-x: auto;
        }
        
        .nav-link {
            padding: 1.2rem 1.5rem;
            text-decoration: none;
            color: var(--dark);
            font-weight: 500;
            transition: all 0.3s ease;
            white-space: nowrap;
        }
        
        .nav-link:hover, .nav-link.active {
            color: var(--accent);
            box-shadow: inset 0 -3px 0 var(--accent);
        }
        
        /* Main Content */
        .container {
            max-width: 1200px;
            margin: 3rem auto;
            padding: 0 2rem;
        }
        
        .section {
            margin-bottom: 4rem;
            padding: 2rem;
            background: white;
            border-radius: 15px;
            box-shadow: 0 5px 25px rgba(0, 0, 0, 0.05);
            border: 1px solid rgba(0, 0, 0, 0.03);
        }
        
        .section-header {
            display: flex;
            align-items: center;
            margin-bottom: 2rem;
            padding-bottom: 1rem;
            border-bottom: 2px solid rgba(26, 35, 126, 0.1);
        }
        
        .section-icon {
            width: 50px;
            height: 50px;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-left: 1rem;
            color: white;
            font-size: 1.5rem;
        }
        
        .section-title {
            font-size: 1.8rem;
            color: var(--primary);
        }
        
        /* Executive Summary */
        .executive-summary {
            font-size: 1.1rem;
            line-height: 1.9;
            text-align: justify;
        }
        
        .highlight {
            background: linear-gradient(120deg, rgba(26, 115, 232, 0.15) 0%, transparent 80%);
            padding: 0.2rem 0.5rem;
            border-radius: 4px;
            font-weight: 500;
        }
        
        /* Timeline */
        .timeline {
            position: relative;
            max-width: 800px;
            margin: 0 auto;
        }
        
        .timeline::before {
            content: '';
            position: absolute;
            top: 0;
            bottom: 0;
            width: 4px;
            background: linear-gradient(to bottom, var(--primary), var(--secondary));
            left: 50%;
            margin-left: -2px;
            border-radius: 10px;
        }
        
        .timeline-item {
            position: relative;
            margin-bottom: 3rem;
            width: 50%;
        }
        
        .timeline-item:nth-child(odd) {
            left: 0;
            padding-right: 3rem;
            text-align: left;
        }
        
        .timeline-item:nth-child(even) {
            left: 50%;
            padding-left: 3rem;
            text-align: right;
        }
        
        .timeline-content {
            background: white;
            padding: 1.5rem;
            border-radius: 12px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.08);
            position: relative;
            border: 1px solid rgba(0, 0, 0, 0.05);
        }
        
        .timeline-year {
            font-size: 1.3rem;
            font-weight: bold;
            color: var(--secondary);
            margin-bottom: 0.5rem;
        }
        
        .timeline-title {
            font-size: 1.2rem;
            margin-bottom: 0.8rem;
            color: var(--dark);
        }
        
        .timeline-desc {
            color: #555;
            font-size: 0.95rem;
        }
        
        /* Skills */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 1.5rem;
        }
        
        .skill-category {
            margin-bottom: 1.5rem;
        }
        
        .skill-title {
            font-size: 1.1rem;
            margin-bottom: 0.8rem;
            color: var(--primary);
        }
        
        .skill-bar {
            height: 8px;
            background: #e0e0e0;
            border-radius: 10px;
            margin-bottom: 1.2rem;
            overflow: hidden;
        }
        
        .skill-progress {
            height: 100%;
            background: linear-gradient(to right, var(--primary), var(--accent));
            border-radius: 10px;
        }
        
        /* Projects */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
            gap: 2rem;
        }
        
        .project-card {
            background: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.08);
            transition: all 0.3s ease;
            border: 1px solid rgba(0, 0, 0, 0.05);
        }
        
        .project-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.15);
        }
        
        .project-header {
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            color: white;
            padding: 1.5rem;
        }
        
        .project-title {
            font-size: 1.3rem;
            margin-bottom: 0.5rem;
        }
        
        .project-body {
            padding: 1.5rem;
        }
        
        .project-desc {
            margin-bottom: 1.2rem;
            color: #555;
        }
        
        .project-tech {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            margin-bottom: 1.5rem;
        }
        
        .tech-tag {
            background: rgba(26, 115, 232, 0.1);
            color: var(--accent);
            padding: 0.3rem 0.8rem;
            border-radius: 50px;
            font-size: 0.85rem;
        }
        
        /* دستاوردهای علمی */
        .achievements-container {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
            gap: 1.5rem;
            margin-top: 1rem;
        }
        
        .achievement {
            display: flex;
            background: rgba(26, 35, 126, 0.05);
            border-radius: 15px;
            padding: 1.5rem;
            transition: transform 0.3s ease;
            border-left: 4px solid var(--primary);
        }
        
        .achievement:hover {
            transform: translateY(-5px);
            background: rgba(26, 35, 126, 0.08);
        }
        
        .achievement-icon {
            font-size: 2rem;
            margin-left: 1rem;
            color: var(--primary);
        }
        
        .achievement-content h3 {
            font-size: 1.2rem;
            margin-bottom: 0.5rem;
            color: var(--dark);
        }
        
        .achievement-content p {
            color: #555;
            font-size: 0.95rem;
        }
        
        /* ارتباطات */
        .contact-container {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 3rem;
        }
        
        @media (max-width: 768px) {
            .contact-container {
                grid-template-columns: 1fr;
            }
        }
        
        .contact-form {
            background: rgba(26, 35, 126, 0.03);
            padding: 1.5rem;
            border-radius: 15px;
        }
        
        .contact-form h3 {
            margin-bottom: 1.5rem;
            color: var(--primary);
        }
        
        .form-group {
            margin-bottom: 1.2rem;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 500;
        }
        
        .form-group input, 
        .form-group select, 
        .form-group textarea {
            width: 100%;
            padding: 0.8rem;
            border: 1px solid #ddd;
            border-radius: 8px;
            font-family: inherit;
            font-size: 1rem;
        }
        
        .submit-btn {
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            color: white;
            border: none;
            padding: 0.8rem 2rem;
            border-radius: 50px;
            cursor: pointer;
            font-size: 1rem;
            font-weight: 500;
            transition: all 0.3s ease;
        }
        
        .submit-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(26, 35, 126, 0.3);
        }
        
        .contact-info {
            background: rgba(49, 27, 146, 0.03);
            padding: 1.5rem;
            border-radius: 15px;
        }
        
        .info-item {
            display: flex;
            align-items: center;
            margin-bottom: 1.5rem;
        }
        
        .info-icon {
            font-size: 1.5rem;
            margin-left: 1rem;
            color: var(--secondary);
        }
        
        .calendar-section {
            background: rgba(76, 175, 80, 0.08);
            padding: 1.5rem;
            border-radius: 12px;
            margin-top: 2rem;
        }
        
        .calendar-section h4 {
            margin-bottom: 0.8rem;
        }
        
        .calendar-btn {
            background: var(--success);
            color: white;
            border: none;
            padding: 0.7rem 1.5rem;
            border-radius: 50px;
            cursor: pointer;
            margin-top: 1rem;
            font-family: inherit;
            font-size: 1rem;
            transition: all 0.3s ease;
        }
        
        .calendar-btn:hover {
            background: #3d8b40;
            transform: translateY(-3px);
        }
        
        /* چشم‌انداز آینده */
        .vision-intro {
            background: rgba(26, 115, 232, 0.05);
            padding: 2rem;
            border-radius: 15px;
            margin-bottom: 2rem;
            text-align: center;
            font-style: italic;
            font-size: 1.1rem;
            border-left: 4px solid var(--accent);
        }
        
        .vision-goals {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 1.5rem;
            margin-bottom: 3rem;
        }
        
        .goal-card {
            background: white;
            padding: 1.5rem;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            border-top: 3px solid var(--primary);
        }
        
        .goal-card h3 {
            margin-bottom: 1rem;
            color: var(--secondary);
        }
        
        .goal-card ul {
            padding-right: 1.5rem;
        }
        
        .goal-card li {
            margin-bottom: 0.8rem;
            font-size: 0.95rem;
            color: #555;
        }
        
        .vision-timeline {
            position: relative;
            padding: 2rem 0;
        }
        
        .vision-timeline::before {
            content: '';
            position: absolute;
            top: 0;
            bottom: 0;
            right: 50%;
            width: 4px;
            background: linear-gradient(to bottom, var(--primary), var(--secondary));
        }
        
        .timeline-milestone {
            position: relative;
            width: 50%;
            padding: 1.5rem;
        }
        
        .timeline-milestone:nth-child(odd) {
            right: 0;
            text-align: left;
        }
        
        .timeline-milestone:nth-child(even) {
            right: 50%;
            text-align: right;
        }
        
        .milestone-year {
            font-weight: bold;
            font-size: 1.2rem;
            color: var(--primary);
            margin-bottom: 0.5rem;
        }
        
        .milestone-dot {
            position: absolute;
            top: 50%;
            width: 20px;
            height: 20px;
            background: var(--accent);
            border: 3px solid white;
            border-radius: 50%;
            box-shadow: 0 0 0 3px var(--accent);
        }
        
        .timeline-milestone:nth-child(odd) .milestone-dot {
            right: -10px;
        }
        
        .timeline-milestone:nth-child(even) .milestone-dot {
            right: calc(100% - 10px);
        }
        
        /* سیستم رویدادها */
        .events-container {
            display: grid;
            grid-template-columns: 300px 1fr;
            gap: 2rem;
        }
        
        @media (max-width: 992px) {
            .events-container {
                grid-template-columns: 1fr;
            }
        }
        
        .events-calendar {
            background: white;
            border-radius: 20px;
            padding: 1.5rem;
            box-shadow: 0 5px 25px rgba(0, 0, 0, 0.05);
        }
        
        .calendar-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 1.5rem;
        }
        
        .calendar-header button {
            background: none;
            border: none;
            font-size: 1.2rem;
            cursor: pointer;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.3s ease;
        }
        
        .calendar-header button:hover {
            background: rgba(26, 115, 232, 0.1);
        }
        
        .calendar-grid {
            display: grid;
            grid-template-columns: repeat(7, 1fr);
            gap: 8px;
        }
        
        .calendar-day {
            height: 40px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 8px;
            font-weight: 500;
            position: relative;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        
        .calendar-day:hover {
            background: rgba(26, 115, 232, 0.1);
        }
        
        .calendar-day.today {
            background: rgba(26, 115, 232, 0.2);
            color: var(--accent);
        }
        
        .calendar-day.has-event:after {
            content: '';
            position: absolute;
            bottom: 5px;
            width: 6px;
            height: 6px;
            background: var(--success);
            border-radius: 50%;
        }
        
        .event-card {
            display: flex;
            background: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.05);
            margin-bottom: 1.5rem;
            transition: all 0.3s ease;
        }
        
        .event-card.featured {
            border-left: 4px solid var(--accent);
        }
        
        .event-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
        }
        
        .event-date {
            min-width: 80px;
            background: rgba(26, 35, 126, 0.05);
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            padding: 1rem;
        }
        
        .event-day {
            font-size: 1.8rem;
            font-weight: bold;
            color: var(--primary);
        }
        
        .event-month {
            font-size: 1rem;
            color: #666;
        }
        
        .event-details {
            padding: 1.5rem;
            flex: 1;
        }
        
        .event-title {
            margin-bottom: 0.5rem;
        }
        
        .event-meta {
            display: flex;
            gap: 1rem;
            color: #666;
            font-size: 0.9rem;
            margin-bottom: 0.8rem;
        }
        
        .event-desc {
            color: #555;
            margin-bottom: 1.2rem;
        }
        
        .event-actions {
            display: flex;
            gap: 0.8rem;
        }
        
        .event-btn {
            padding: 0.5rem 1.2rem;
            border: none;
            border-radius: 30px;
            cursor: pointer;
            font-size: 0.9rem;
            transition: all 0.3s ease;
        }
        
        .event-btn.register {
            background: var(--accent);
            color: white;
        }
        
        .event-btn.remind {
            background: rgba(76, 175, 80, 0.1);
            color: var(--success);
        }
        
        /* سیستم پوشش رسانه‌ای */
        .media-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
            gap: 1.5rem;
        }
        
        .media-item {
            background: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.05);
            display: flex;
            flex-direction: column;
        }
        
        .media-thumbnail {
            position: relative;
            height: 200px;
            overflow: hidden;
        }
        
        .media-thumbnail img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: all 0.5s ease;
        }
        
        .media-item:hover .media-thumbnail img {
            transform: scale(1.05);
        }
        
        .play-icon {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 60px;
            height: 60px;
            background: rgba(255, 255, 255, 0.8);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            opacity: 0.9;
            transition: all 0.3s ease;
        }
        
        .media-item:hover .play-icon {
            background: var(--accent);
            color: white;
            opacity: 1;
            transform: translate(-50%, -50%) scale(1.1);
        }
        
        .media-badge {
            position: absolute;
            top: 1rem;
            left: 1rem;
            background: var(--dark);
            color: white;
            padding: 0.3rem 0.8rem;
            border-radius: 30px;
            font-size: 0.8rem;
        }
        
        .media-content {
            padding: 1.5rem;
        }
        
        .media-title {
            margin-bottom: 0.5rem;
        }
        
        .media-meta {
            display: flex;
            gap: 1rem;
            color: #666;
            font-size: 0.9rem;
            margin-bottom: 0.8rem;
        }
        
        .media-desc {
            color: #555;
        }
        
        /* سیستم همکاری */
        .collaboration-cards {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 2rem;
        }
        
        .collab-card {
            background: white;
            border-radius: 20px;
            padding: 2rem;
            box-shadow: 0 10px 40px rgba(0, 0, 0, 0.08);
            text-align: center;
            transition: all 0.3s ease;
            border-top: 4px solid var(--primary);
        }
        
        .collab-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 50px rgba(0, 0, 0, 0.15);
        }
        
        .collab-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
            color: var(--primary);
        }
        
        .collab-title {
            margin-bottom: 1rem;
            color: var(--dark);
        }
        
        .collab-desc {
            color: #555;
            margin-bottom: 1.2rem;
        }
        
        .collab-card ul {
            text-align: right;
            padding-right: 1.5rem;
            margin-bottom: 1.5rem;
            color: #555;
        }
        
        .collab-card li {
            margin-bottom: 0.8rem;
            position: relative;
        }
        
        .collab-card li:before {
            content: '•';
            position: absolute;
            right: -1.2rem;
            color: var(--accent);
        }
        
        .collab-btn {
            background: var(--primary);
            color: white;
            border: none;
            padding: 0.8rem 1.8rem;
            border-radius: 30px;
            cursor: pointer;
            font-size: 1rem;
            transition: all 0.3s ease;
        }
        
        .collab-btn:hover {
            background: var(--secondary);
            transform: translateY(-3px);
        }
        
        /* سیستم تحلیل‌ها */
        .analytics-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            gap: 1.5rem;
            margin-bottom: 2rem;
        }
        
        .metric-card {
            background: white;
            border-radius: 15px;
            padding: 1.5rem;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.05);
            text-align: center;
        }
        
        .metric-value {
            font-size: 2.5rem;
            font-weight: bold;
            color: var(--primary);
            margin-bottom: 0.5rem;
        }
        
        .metric-label {
            color: #666;
            margin-bottom: 0.5rem;
        }
        
        .metric-trend {
            font-size: 0.9rem;
            font-weight: 500;
        }
        
        .metric-trend.up {
            color: var(--success);
        }
        
        .metric-trend.down {
            color: #e53935;
        }
        
        .analytics-charts {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 2rem;
            margin-bottom: 2rem;
        }
        
        .chart-container {
            background: white;
            border-radius: 15px;
            padding: 1.5rem;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.05);
        }
        
        .content-performance {
            background: white;
            border-radius: 15px;
            padding: 1.5rem;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.05);
        }
        
        .performance-table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 1rem;
        }
        
        .performance-table th,
        .performance-table td {
            padding: 1rem;
            text-align: right;
            border-bottom: 1px solid rgba(0, 0, 0, 0.05);
        }
        
        .performance-table th {
            background: rgba(26, 115, 232, 0.05);
            color: var(--primary);
        }
        
        .performance-table tr:hover {
            background: rgba(26, 115, 232, 0.03);
        }
        
        /* سیستم انتخاب زبان */
        .language-switcher {
            position: fixed;
            bottom: 20px;
            left: 20px;
            background: rgba(255, 255, 255, 0.9);
            backdrop-filter: blur(10px);
            border-radius: 30px;
            padding: 0.5rem;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            z-index: 1000;
            display: flex;
            gap: 5px;
        }
        
        .lang-btn {
            padding: 0.5rem 1rem;
            border: none;
            border-radius: 30px;
            background: none;
            cursor: pointer;
            font-size: 0.9rem;
            transition: all 0.3s ease;
        }
        
        .lang-btn.active {
            background: var(--primary);
            color: white;
        }
        
        /* سیستم تغییر حالت تاریک */
        .theme-switcher {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background: rgba(255, 255, 255, 0.9);
            backdrop-filter: blur(10px);
            border-radius: 30px;
            padding: 0.5rem 1rem;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            z-index: 1000;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .switch {
            position: relative;
            display: inline-block;
            width: 50px;
            height: 24px;
        }
        
        .switch input {
            opacity: 0;
            width: 0;
            height: 0;
        }
        
        .slider {
            position: absolute;
            cursor: pointer;
            top: 0;
            right: 0;
            bottom: 0;
            left: 0;
            background-color: #ccc;
            transition: .4s;
            border-radius: 24px;
        }
        
        .slider:before {
            position: absolute;
            content: "";
            height: 16px;
            width: 16px;
            left: 4px;
            bottom: 4px;
            background-color: white;
            transition: .4s;
            border-radius: 50%;
        }
        
        input:checked + .slider {
            background-color: var(--primary);
        }
        
        input:checked + .slider:before {
            transform: translateX(26px);
        }
        
        /* مدال احراز هویت */
        #auth-modal {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(0, 0, 0, 0.7);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 1000;
        }
        
        .modal-content {
            background: white;
            padding: 2rem;
            border-radius: 15px;
            text-align: center;
            width: 90%;
            max-width: 500px;
        }
        
        .camera-feed {
            width: 100%;
            height: 300px;
            background: #eee;
            margin: 1.5rem 0;
            border-radius: 10px;
            overflow: hidden;
            position: relative;
        }
        
        #auth-video {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        
        .face-indicator {
            font-size: 5rem;
            margin: 1rem 0;
            animation: pulse 1.5s infinite;
        }
        
        @keyframes pulse {
            0% { opacity: 0.7; transform: scale(1); }
            50% { opacity: 1; transform: scale(1.05); }
            100% { opacity: 0.7; transform: scale(1); }
        }
        
        #cancel-auth {
            background: #e53935;
            color: white;
            border: none;
            padding: 0.7rem 1.5rem;
            border-radius: 50px;
            cursor: pointer;
            margin-top: 1rem;
            font-family: inherit;
            font-size: 1rem;
        }
        
        /* Footer */
        .footer {
            background: var(--dark);
            color: rgba(255, 255, 255, 0.7);
            padding: 3rem 2rem;
            text-align: center;
        }
        
        .digital-signature {
            font-size: 1.2rem;
            font-style: italic;
            margin: 2rem 0;
            color: white;
            opacity: 0.9;
        }
        
        .social-links {
            display: flex;
            justify-content: center;
            gap: 1.5rem;
            margin: 1.5rem 0;
        }
        
        .social-link {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.1);
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.3s ease;
            color: white;
            font-size: 1.2rem;
            text-decoration: none;
        }
        
        .social-link:hover {
            background: var(--accent);
            transform: translateY(-5px);
        }
        
        .copyright {
            margin-top: 2rem;
            font-size: 0.9rem;
            opacity: 0.6;
        }
        
        /* Responsive Design */
        @media (max-width: 992px) {
            .events-container {
                grid-template-columns: 1fr;
            }
            
            .analytics-charts {
                grid-template-columns: 1fr;
            }
            
            .timeline::before {
                left: 30px;
            }
            
            .timeline-item {
                width: 100% !important;
                padding-left: 70px !important;
                padding-right: 0 !important;
            }
        }
        
        @media (max-width: 768px) {
            .projects-grid {
                grid-template-columns: 1fr;
            }
            
            .achievements-container {
                grid-template-columns: 1fr;
            }
            
            .contact-container {
                grid-template-columns: 1fr;
            }
            
            .vision-goals {
                grid-template-columns: 1fr;
            }
            
            .nav-container {
                justify-content: flex-start;
            }
            
            .profile-title {
                font-size: 2rem;
            }
            
            .profile-subtitle {
                font-size: 1.1rem;
            }
        }
    </style>
</head>
<body>
    <!-- Header Section -->
    <header class="profile-header">
        <div class="header-pattern"></div>
        <div class="avatar-container">
            <div class="avatar">QH</div>
        </div>
        <h1 class="profile-title">قیس حیدری</h1>
        <h2 class="profile-subtitle">بنیانگذار و معمار ارشد هوش مصنوعی | QH-SMART AI</h2>
        
        <div class="badges-container">
            <div class="badge"><i class="fas fa-microscope"></i> پژوهشگر برتر IEEE 2024</div>
            <div class="badge"><i class="fas fa-trophy"></i> برنده جایزه یونسکو</div>
            <div class="badge"><i class="fas fa-code"></i> 10+ سال تجربه در AI</div>
        </div>
    </header>

    <!-- Navigation -->
    <nav class="profile-nav">
        <div class="nav-container">
            <a href="#summary" class="nav-link active">خلاصه اجرایی</a>
            <a href="#journey" class="nav-link">سفر حرفه‌ای</a>
            <a href="#skills" class="nav-link">مهارت‌های کلیدی</a>
            <a href="#projects" class="nav-link">پروژه‌های شاخص</a>
            <a href="#achievements" class="nav-link">دستاوردهای علمی</a>
            <a href="#contact" class="nav-link">ارتباطات</a>
            <a href="#vision" class="nav-link">چشم‌انداز آینده</a>
            <a href="#events" class="nav-link">رویدادها</a>
            <a href="#media" class="nav-link">پوشش رسانه‌ای</a>
            <a href="#collaborate" class="nav-link">همکاری</a>
        </div>
    </nav>

    <!-- Main Content -->
    <main class="container">
        <!-- Executive Summary -->
        <section id="summary" class="section">
            <div class="section-header">
                <div class="section-icon"><i class="fas fa-file-alt"></i></div>
                <h2 class="section-title">خلاصه اجرایی</h2>
            </div>
            <div class="executive-summary">
                <p>مهندس هوش مصنوعی با <span class="highlight">۱۰+ سال تجربه</span> در طراحی سیستم‌های یادگیری عمیق و پردازش زبان طبیعی (NLP). متخصص در توسعه راهکارهای هوش مصنوعی تحول‌آفرین با تمرکز بر سیستم‌های خودآموز و اخلاق‌محور.</p>
                
                <p>مأموریت اصلی: <span class="highlight">دموکراتیزه‌سازی دسترسی به فناوری‌های هوشمند</span> از طریق توسعه پلتفرم‌های مقیاس‌پذیر و قابل تفسیر. ترکیبی از تخصص فنی (پژوهش در دانشگاه‌های تراز اول جهانی) و تجربه رهبری پروژه‌های کلان صنعتی.</p>
                
                <p>پیشگام در ایجاد <span class="highlight">پلتفرم‌های آموزشی مبتنی بر هوش مصنوعی</span> برای افراد با نیازهای ویژه در افغانستان و منطقه. متعهد به توسعه راهکارهای فناورانه با تأثیر اجتماعی مثبت و پایدار.</p>
            </div>
        </section>

        <!-- Professional Journey -->
        <section id="journey" class="section">
            <div class="section-header">
                <div class="section-icon"><i class="fas fa-road"></i></div>
                <h2 class="section-title">سفر حرفه‌ای</h2>
            </div>
            <div class="timeline">
                <div class="timeline-item">
                    <div class="timeline-content">
                        <div class="timeline-year">۲۰۲۵ - اکنون</div>
                        <h3 class="timeline-title">بنیانگذار QH-SMART AI</h3>
                        <p class="timeline-desc">توسعه چارچوب هوش مصنوعی خودسازمان‌ده برای تشخیص پزشکی با تمرکز بر بیماری‌های بومی منطقه</p>
                    </div>
                </div>
                
                <div class="timeline-item">
                    <div class="timeline-content">
                        <div class="timeline-year">۲۰۲۳ - ۲۰۲۵</div>
                        <h3 class="timeline-title">رئیس بخش پژوهش‌های AI در TechGlobal Inc.</h3>
                        <p class="timeline-desc">رهبری تیم ۱۵ نفره در پروژه‌های بین‌المللی با تمرکز بر سیستم‌های توصیه‌گر پیشرفته</p>
                    </div>
                </div>
                
                <div class="timeline-item">
                    <div class="timeline-content">
                        <div class="timeline-year">۲۰۲۰ - ۲۰۲۳</div>
                        <h3 class="timeline-title">پژوهشگر ارشد دانشگاه MIT</h3>
                        <p class="timeline-desc">تمرکز بر Explainable AI در سیستم‌های امنیتی و توسعه مدل‌های تفسیرپذیر</p>
                    </div>
                </div>
                
                <div class="timeline-item">
                    <div class="timeline-content">
                        <div class="timeline-year">۲۰۱۸ - ۲۰۲۰</div>
                        <h3 class="timeline-title">مهندس یادگیری ماشین در Amazon</h3>
                        <p class="timeline-desc">بهینه‌سازی الگوریتم‌های پیشنهادگر با استفاده از تکنیک‌های یادگیری تقویتی</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- Key Skills -->
        <section id="skills" class="section">
            <div class="section-header">
                <div class="section-icon"><i class="fas fa-rocket"></i></div>
                <h2 class="section-title">مهارت‌های کلیدی</h2>
            </div>
            <div class="skills-grid">
                <div class="skill-category">
                    <h3 class="skill-title">هوش مصنوعی و یادگیری ماشین</h3>
                    <div class="skill-bar">
                        <div class="skill-progress" style="width: 95%"></div>
                    </div>
                    
                    <h3 class="skill-title">پردازش زبان طبیعی (NLP)</h3>
                    <div class="skill-bar">
                        <div class="skill-progress" style="width: 90%"></div>
                    </div>
                    
                    <h3 class="skill-title">بینایی ماشین</h3>
                    <div class="skill-bar">
                        <div class="skill-progress" style="width: 85%"></div>
                    </div>
                </div>
                
                <div class="skill-category">
                    <h3 class="skill-title">توسعه پلتفرم‌های ابری</h3>
                    <div class="skill-bar">
                        <div class="skill-progress" style="width: 80%"></div>
                    </div>
                    
                    <h3 class="skill-title">هوش مصنوعی تولیدی (GANs, Transformers)</h3>
                    <div class="skill-bar">
                        <div class="skill-progress" style="width: 88%"></div>
                    </div>
                    
                    <h3 class="skill-title">مهندسی داده‌های کلان</h3>
                    <div class="skill-bar">
                        <div class="skill-progress" style="width: 75%"></div>
                    </div>
                </div>
                
                <div class="skill-category">
                    <h3 class="skill-title">رهبری تیم‌های فنی</h3>
                    <div class="skill-bar">
                        <div class="skill-progress" style="width: 90%"></div>
                    </div>
                    
                    <h3 class="skill-title">طراحی معماری سیستم‌های هوشمند</h3>
                    <div class="skill-bar">
                        <div class="skill-progress" style="width: 92%"></div>
                    </div>
                    
                    <h3 class="skill-title">اخلاق در هوش مصنوعی</h3>
                    <div class="skill-bar">
                        <div class="skill-progress" style="width: 96%"></div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Highlighted Projects -->
        <section id="projects" class="section">
            <div class="section-header">
                <div class="section-icon"><i class="fas fa-briefcase"></i></div>
                <h2 class="section-title">پروژه‌های شاخص</h2>
            </div>
            <div class="projects-grid">
                <div class="project-card">
                    <div class="project-header">
                        <h3 class="project-title">پروژه MED-SCAN</h3>
                        <p>سیستم تشخیص تومور با تفسیرپذیری بالین</p>
                    </div>
                    <div class="project-body">
                        <p class="project-desc">پلتفرم هوش مصنوعی برای تشخیص زودهنگام تومورها با استفاده از ترکیب Vision Transformers و یادگیری نیمه‌نظارتی. کاهش ۴۰٪ خطای تشخیصی در داده‌های بالینی.</p>
                        <div class="project-tech">
                            <span class="tech-tag">TensorFlow</span>
                            <span class="tech-tag">PyTorch</span>
                            <span class="tech-tag">DICOM</span>
                        </div>
                    </div>
                </div>
                
                <div class="project-card">
                    <div class="project-header">
                        <h3 class="project-title">پروژه LINGUA</h3>
                        <p>پلتفرم ترجمه بیدرنگ برای زبان‌های کم‌منبع</p>
                    </div>
                    <div class="project-body">
                        <p class="project-desc">سیستم ترجمه چندزبانه با پشتیبانی از ۱۲ زبان محلی با دقت ۹۴%. برنده جایزه یونسکو ۲۰۲۴ برای حفظ زبان‌های در معرض خطر.</p>
                        <div class="project-tech">
                            <span class="tech-tag">NLP</span>
                            <span class="tech-tag">Transformers</span>
                            <span class="tech-tag">AWS</span>
                        </div>
                    </div>
                </div>
                
                <div class="project-card">
                    <div class="project-header">
                        <h3 class="project-title">پروژه EDU-BOT</h3>
                        <p>شبکه چت‌بات‌های آموزشی برای نیازهای ویژه</p>
                    </div>
                    <div class="project-body">
                        <p class="project-desc">پلتفرم آموزش مجازی مبتنی بر هوش مصنوعی با پشتیبانی از زبان اشاره و رابط‌های صوتی برای نابینایان و ناشنوایان.</p>
                        <div class="project-tech">
                            <span class="tech-tag">ChatGPT API</span>
                            <span class="tech-tag">Computer Vision</span>
                            <span class="tech-tag">Speech Recognition</span>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Scientific Achievements -->
        <section id="achievements" class="section">
            <div class="section-header">
                <div class="section-icon"><i class="fas fa-trophy"></i></div>
                <h2 class="section-title">دستاوردهای علمی</h2>
            </div>
            
            <div class="achievements-container">
                <div class="achievement">
                    <div class="achievement-icon"><i class="fas fa-book"></i></div>
                    <div class="achievement-content">
                        <h3>نویسنده برتر نشریه IEEE 2024</h3>
                        <p>مقالۀ "معماری شبکه‌های عصبی خودسازمان‌ده برای تشخیص پزشکی" با بیشترین ارجاع در حوزه هوش مصنوعی سلامت</p>
                    </div>
                </div>
                
                <div class="achievement">
                    <div class="achievement-icon"><i class="fas fa-globe-asia"></i></div>
                    <div class="achievement-content">
                        <h3>برنده جایزه یونسکو برای فناوری‌های فراگیر</h3>
                        <p>طراحی پلتفرم آموزشی چندحسی برای کودکان با نیازهای ویژه در مناطق محروم</p>
                    </div>
                </div>
                
                <div class="achievement">
                    <div class="achievement-icon"><i class="fas fa-flask"></i></div>
                    <div class="achievement-content">
                        <h3>دارای ۱۲ ثبت اختراع بین‌المللی</h3>
                        <p>اختراعات در حوزه‌های یادگیری انتقالی، مدل‌های ترکیبی و سیستم‌های توصیه‌گر هوشمند</p>
                    </div>
                </div>
                
                <div class="achievement">
                    <div class="achievement-icon"><i class="fas fa-graduation-cap"></i></div>
                    <div class="achievement-content">
                        <h3>استاد مدعو دانشگاه‌های استنفورد و MIT</h3>
                        <p>ارائه دوره‌های تخصصی "اخلاق در هوش مصنوعی" و "معماری سیستم‌های خودآموز"</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- Contact -->
        <section id="contact" class="section">
            <div class="section-header">
                <div class="section-icon"><i class="fas fa-envelope"></i></div>
                <h2 class="section-title">ارتباطات</h2>
            </div>
            
            <div class="contact-container">
                <div class="contact-form">
                    <h3>ارسال پیام</h3>
                    <form id="messageForm">
                        <div class="form-group">
                            <label for="name">نام کامل</label>
                            <input type="text" id="name" required>
                        </div>
                        
                        <div class="form-group">
                            <label for="email">ایمیل</label>
                            <input type="email" id="email" required>
                        </div>
                        
                        <div class="form-group">
                            <label for="subject">موضوع</label>
                            <select id="subject">
                                <option value="collaboration">همکاری پژوهشی</option>
                                <option value="speaking">سخنرانی و کارگاه</option>
                                <option value="consulting">مشاوره فنی</option>
                                <option value="media">درخواست رسانه‌ای</option>
                            </select>
                        </div>
                        
                        <div class="form-group">
                            <label for="message">پیام</label>
                            <textarea id="message" rows="5" required></textarea>
                        </div>
                        
                        <button type="submit" class="submit-btn">ارسال پیام</button>
                    </form>
                </div>
                
                <div class="contact-info">
                    <h3>اطلاعات تماس</h3>
                    <div class="info-item">
                        <div class="info-icon"><i class="fas fa-envelope"></i></div>
                        <p>contact@qhaidari.ai</p>
                    </div>
                    
                    <div class="info-item">
                        <div class="info-icon"><i class="fas fa-building"></i></div>
                        <p>دفتر مرکزی: برج خلیفه، دبی، امارات متحده عربی</p>
                    </div>
                    
                    <div class="info-item">
                        <div class="info-icon"><i class="fas fa-globe"></i></div>
                        <p>مرکز پژوهش‌های هوش مصنوعی: کابل، افغانستان</p>
                    </div>
                    
                    <div class="calendar-section">
                        <h4>زمان‌های مشاوره</h4>
                        <p>دوشنبه و چهارشنبه: ۱۴:۰۰ تا ۱۷:۰۰ (به وقت دبی)</p>
                        <button id="scheduleBtn" class="calendar-btn">
                            <i class="fas fa-calendar-alt"></i> رزرو زمان مشاوره
                        </button>
                    </div>
                </div>
            </div>
        </section>

        <!-- Future Vision -->
        <section id="vision" class="section">
            <div class="section-header">
                <div class="section-icon"><i class="fas fa-binoculars"></i></div>
                <h2 class="section-title">چشم‌انداز آینده</h2>
            </div>
            
            <div class="vision-content">
                <div class="vision-intro">
                    <p>"توسعه هوش مصنوعی نباید صرفاً رقابتی فناورانه باشد، بلکه باید سفری انسانی برای افزایش قابلیت‌های بشر و ایجاد فرصت‌های برابر باشد."</p>
                </div>
                
                <div class="vision-goals">
                    <div class="goal-card">
                        <h3>پلتفرم آموزش هوشمند QH-EDU</h3>
                        <ul>
                            <li>دسترسی رایگان به آموزش‌های تخصصی هوش مصنوعی برای ۱۰۰,۰۰۰ دانشجوی منطقه تا ۲۰۳۰</li>
                            <li>توسعه سیستم‌های آموزشی تطبیقی مبتنی بر هوش مصنوعی با پشتیبانی از ۱۵ زبان محلی</li>
                        </ul>
                    </div>
                    
                    <div class="goal-card">
                        <h3>مرکز نوآوری‌های سلامت QH-HEALTH</h3>
                        <ul>
                            <li>کاهش ۵۰٪ خطاهای تشخیص پزشکی در مناطق محروم تا ۲۰۲۸</li>
                            <li>توسعه سامانه‌های پیش‌بینی شیوع بیماری‌های منطقه‌ای با دقت ۹۵٪</li>
                        </ul>
                    </div>
                    
                    <div class="goal-card">
                        <h3>پروژه حفظ زبان‌های در معرض خطر</h3>
                        <ul>
                            <li>ثبت دیجیتال و احیای ۲۰ زبان در معرض انقراض تا ۲۰۲۷</li>
                            <li>توسعه مدل‌های زبانی بزرگ برای زبان‌های کم‌منبع</li>
                        </ul>
                    </div>
                </div>
                
                <div class="vision-timeline">
                    <div class="timeline-milestone">
                        <div class="milestone-year">۲۰۲۵</div>
                        <div class="milestone-dot"></div>
                        <div class="milestone-text">راه‌اندازی آزمایشگاه‌های هوش مصنوعی در کابل و هرات</div>
                    </div>
                    
                    <div class="timeline-milestone">
                        <div class="milestone-year">۲۰۲۷</div>
                        <div class="milestone-dot"></div>
                        <div class="milestone-text">توسعه سوپرکامپیوتر بومی برای آموزش مدل‌های بزرگ</div>
                    </div>
                    
                    <div class="timeline-milestone">
                        <div class="milestone-year">۲۰۳۰</div>
                        <div class="milestone-dot"></div>
                        <div class="milestone-text">ایجاد قطب منطقه‌ای هوش مصنوعی با تمرکز بر راهکارهای توسعه پایدار</div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Events -->
        <section id="events" class="section">
            <div class="section-header">
                <div class="section-icon"><i class="fas fa-calendar-alt"></i></div>
                <h2 class="section-title">رویدادهای پیش‌رو و سخنرانی‌ها</h2>
            </div>
            
            <div class="events-container">
                <div class="events-calendar">
                    <div class="calendar-header">
                        <button id="prev-month"><i class="fas fa-chevron-left"></i></button>
                        <h3 id="current-month">تیر ۱۴۰۴</h3>
                        <button id="next-month"><i class="fas fa-chevron-right"></i></button>
                    </div>
                    <div class="calendar-grid" id="calendar-grid">
                        <!-- روزهای تقویم به صورت پویا تولید می‌شوند -->
                    </div>
                </div>
                
                <div class="events-list">
                    <div class="event-card featured">
                        <div class="event-date">
                            <div class="event-day">۱۵</div>
                            <div class="event-month">تیر</div>
                        </div>
                        <div class="event-details">
                            <h3 class="event-title">کنفرانس جهانی هوش مصنوعی اخلاق‌محور</h3>
                            <div class="event-meta">
                                <span><i class="fas fa-map-marker-alt"></i> دبی، مرکز تجارت جهانی</span>
                                <span><i class="fas fa-clock"></i> ۱۴:۰۰ تا ۱۷:۰۰</span>
                            </div>
                            <p class="event-desc">سخنرانی کلیدی با موضوع "چارچوب‌های حکمرانی هوش مصنوعی در جهان در حال توسعه"</p>
                            <div class="event-actions">
                                <button class="event-btn register"><i class="fas fa-user-plus"></i> ثبت‌نام رایگان</button>
                                <button class="event-btn remind"><i class="fas fa-bell"></i> یادآوری</button>
                            </div>
                        </div>
                    </div>
                    
                    <div class="event-card">
                        <div class="event-date">
                            <div class="event-day">۲۲</div>
                            <div class="event-month">تیر</div>
                        </div>
                        <div class="event-details">
                            <h3 class="event-title">کارگاه عملی Transformerها</h3>
                            <div class="event-meta">
                                <span><i class="fas fa-globe"></i> آنلاین (زنده)</span>
                                <span><i class="fas fa-clock"></i> ۱۸:۰۰ تا ۲۱:۰۰</span>
                            </div>
                            <p class="event-desc">آموزش عملی پیاده‌سازی مدل‌های زبانی بزرگ برای مسائل حوزه سلامت</p>
                            <div class="event-actions">
                                <button class="event-btn register"><i class="fas fa-user-plus"></i> ثبت‌نام</button>
                                <button class="event-btn materials"><i class="fas fa-book"></i> مواد آموزشی</button>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Media Coverage -->
        <section id="media" class="section">
            <div class="section-header">
                <div class="section-icon"><i class="fas fa-newspaper"></i></div>
                <h2 class="section-title">پوشش رسانه‌ای</h2>
            </div>
            
            <div class="media-tabs">
                <div class="tab-header">
                    <button class="tab-link active" data-tab="interviews">مصاحبه‌ها</button>
                    <button class="tab-link" data-tab="articles">مقالات</button>
                    <button class="tab-link" data-tab="podcasts">پادکست‌ها</button>
                    <button class="tab-link" data-tab="awards">جوایز</button>
                </div>
                
                <div class="tab-content">
                    <div id="interviews" class="tab-pane active">
                        <div class="media-grid">
                            <div class="media-item video">
                                <div class="media-thumbnail">
                                    <div class="placeholder-thumbnail" style="background: linear-gradient(45deg, #1a237e, #4fc3f7); display: flex; align-items: center; justify-content: center; height: 100%; color: white; font-size: 2rem;">
                                        <i class="fas fa-play-circle"></i>
                                    </div>
                                    <div class="play-icon">▶</div>
                                    <div class="media-badge">ویدیو</div>
                                </div>
                                <div class="media-content">
                                    <h3 class="media-title">مصاحبه اختصاصی با شبکه CNN</h3>
                                    <div class="media-meta">
                                        <span>CNN Technology</span>
                                        <span>۱۵ خرداد ۱۴۰۴</span>
                                    </div>
                                    <p class="media-desc">"تأثیر هوش مصنوعی بر نظام سلامت در کشورهای در حال توسعه" - تحلیل قیس حیدری از چالش‌ها و فرصت‌ها</p>
                                </div>
                            </div>
                            
                            <div class="media-item audio">
                                <div class="media-thumbnail">
                                    <div class="placeholder-thumbnail" style="background: linear-gradient(45deg, #311b92, #ab47bc); display: flex; align-items: center; justify-content: center; height: 100%; color: white; font-size: 2rem;">
                                        <i class="fas fa-podcast"></i>
                                    </div>
                                    <div class="play-icon">🔊</div>
                                    <div class="media-badge">صوتی</div>
                                </div>
                                <div class="media-content">
                                    <h3 class="media-title">برنامه ویژه رادیو BBC</h3>
                                    <div class="media-meta">
                                        <span>BBC World Service</span>
                                        <span>۲ اردیبهشت ۱۴۰۴</span>
                                    </div>
                                    <p class="media-desc">بحث در مورد اخلاق هوش مصنوعی و خطرات مدل‌های تولیدی غیرقابل کنترل</p>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Collaboration -->
        <section id="collaborate" class="section">
            <div class="section-header">
                <div class="section-icon"><i class="fas fa-handshake"></i></div>
                <h2 class="section-title">همکاری در پروژه‌های تحقیقاتی</h2>
            </div>
            
            <div class="collaboration-cards">
                <div class="collab-card">
                    <div class="collab-icon"><i class="fas fa-search"></i></div>
                    <h3 class="collab-title">پژوهشگران</h3>
                    <p class="collab-desc">همکاری در پروژه‌های تحقیقاتی بین‌المللی در حوزه‌های:</p>
                    <ul>
                        <li>هوش مصنوعی تفسیرپذیر (XAI)</li>
                        <li>مدل‌های زبانی کم‌منبع</li>
                        <li>یادگیری انتقالی در پزشکی</li>
                    </ul>
                    <button class="collab-btn"><i class="fas fa-paper-plane"></i> ارسال پیشنهاد</button>
                </div>
                
                <div class="collab-card">
                    <div class="collab-icon"><i class="fas fa-building"></i></div>
                    <h3 class="collab-title">شرکت‌ها</h3>
                    <p class="collab-desc">همکاری در پیاده‌سازی راهکارهای هوش مصنوعی در صنایع:</p>
                    <ul>
                        <li>سلامت و تشخیص پزشکی</li>
                        <li>آموزش و سیستم‌های یادگیری</li>
                        <li>زبان‌شناسی محاسباتی</li>
                    </ul>
                    <button class="collab-btn"><i class="fas fa-paper-plane"></i> درخواست همکاری</button>
                </div>
                
                <div class="collab-card">
                    <div class="collab-icon"><i class="fas fa-user-graduate"></i></div>
                    <h3 class="collab-title">دانشجویان</h3>
                    <p class="collab-desc">فرصت‌های تحقیقاتی و کارآموزی در زمینه‌های:</p>
                    <ul>
                        <li>یادگیری عمیق پیشرفته</li>
                        <li>پردازش زبان طبیعی</li>
                        <li>بینایی ماشین پزشکی</li>
                    </ul>
                    <button class="collab-btn"><i class="fas fa-paper-plane"></i> ارسال رزومه</button>
                </div>
            </div>
        </section>

        <!-- Analytics (Visible after authentication) -->
        <section id="analytics" class="section" style="display:none">
            <div class="section-header">
                <div class="section-icon"><i class="fas fa-chart-bar"></i></div>
                <h2 class="section-title">تحلیل تعاملات پروفایل</h2>
            </div>
            
            <div class="analytics-grid">
                <div class="metric-card">
                    <div class="metric-value" id="total-visits">۱,۲۴۸</div>
                    <div class="metric-label">بازدید کل</div>
                    <div class="metric-trend up">+۱۲٫۷٪ <i class="fas fa-arrow-up"></i></div>
                </div>
                
                <div class="metric-card">
                    <div class="metric-value" id="unique-visitors">۸۹۳</div>
                    <div class="metric-label">بازدیدکننده منحصر به فرد</div>
                    <div class="metric-trend up">+۸٫۳٪ <i class="fas fa-arrow-up"></i></div>
                </div>
                
                <div class="metric-card">
                    <div class="metric-value" id="downloads">۳۴۷</div>
                    <div class="metric-label">دانلود پژوهش‌ها</div>
                    <div class="metric-trend up">+۲۱٫۴٪ <i class="fas fa-arrow-up"></i></div>
                </div>
                
                <div class="metric-card">
                    <div class="metric-value" id="contact-requests">۸۶</div>
                    <div class="metric-label">درخواست تماس</div>
                    <div class="metric-trend down">-۳٫۲٪ <i class="fas fa-arrow-down"></i></div>
                </div>
            </div>
            
            <div class="analytics-charts">
                <div class="chart-container">
                    <h3>توزیع جغرافیایی بازدیدکنندگان</h3>
                    <div style="height: 300px; display: flex; align-items: center; justify-content: center; background: #f8f9fa; border-radius: 10px; color: #666;">
                        نقشه جغرافیایی (فعال پس از احراز هویت)
                    </div>
                </div>
                
                <div class="chart-container">
                    <h3>روند تعاملات در ۳۰ روز گذشته</h3>
                    <canvas id="engagement-chart"></canvas>
                </div>
            </div>
            
            <div class="content-performance">
                <h3>پربازدیدترین محتواها</h3>
                <table class="performance-table">
                    <thead>
                        <tr>
                            <th>عنوان محتوا</th>
                            <th>بازدید</th>
                            <th>زمان ماندگاری</th>
                            <th>نرخ تبدیل</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>پروژه MED-SCAN</td>
                            <td>۴۸۹</td>
                            <td>۴:۲۵ دقیقه</td>
                            <td>۱۸٫۷٪</td>
                        </tr>
                        <tr>
                            <td>مقاله IEEE 2024</td>
                            <td>۳۲۷</td>
                            <td>۶:۱۲ دقیقه</td>
                            <td>۲۲٫۳٪</td>
                        </tr>
                        <tr>
                            <td>کارگاه Transformerها</td>
                            <td>۲۸۵</td>
                            <td>۵:۳۰ دقیقه</td>
                            <td>۱۵٫۲٪</td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </section>
    </main>

    <!-- Footer -->
    <footer class="footer">
        <p class="digital-signature">"هوش مصنوعی زمانی ارزشمند است که دانش را به خدمت بگیرد، نه جایگزین آن شود."</p>
        
        <div class="social-links">
            <a href="https://linkedin.com/in/qhaidari" class="social-link"><i class="fab fa-linkedin-in"></i></a>
            <a href="https://github.com/qh-smart" class="social-link"><i class="fab fa-github"></i></a>
            <a href="https://youtube.com/QH-AI-Lectures" class="social-link"><i class="fab fa-youtube"></i></a>
            <a href="https://twitter.com/qh_ai" class="social-link"><i class="fab fa-twitter"></i></a>
            <a href="https://instagram.com/qhaidari_ai" class="social-link"><i class="fab fa-instagram"></i></a>
        </div>
        
        <p>تماس: contact@qhaidari.ai | دبی، امارات متحده عربی</p>
        <p class="copyright">سیستم هوش مصنوعی بومی افغانستان | © ۲۰۲۴ QH VisionX</p>
    </footer>

    <!-- Language Switcher -->
    <div class="language-switcher">
        <button class="lang-btn active" data-lang="fa"><i class="fas fa-language"></i> فارسی</button>
        <button class="lang-btn" data-lang="en"><i class="fas fa-language"></i> English</button>
        <button class="lang-btn" data-lang="ar"><i class="fas fa-language"></i> العربية</button>
    </div>

    <!-- Dark Mode Toggle -->
    <div class="theme-switcher">
        <label class="switch">
            <input type="checkbox" id="dark-mode-toggle">
            <span class="slider"></span>
        </label>
        <span class="theme-label"><i class="fas fa-moon"></i> حالت شب</span>
    </div>

    <script>
        // Navigation active state
        document.addEventListener('DOMContentLoaded', function() {
            const navLinks = document.querySelectorAll('.nav-link');
            const sections = document.querySelectorAll('section');
            
            window.addEventListener('scroll', function() {
                let current = '';
                
                sections.forEach(section => {
                    const sectionTop = section.offsetTop;
                    const sectionHeight = section.clientHeight;
                    
                    if (pageYOffset >= (sectionTop - 200)) {
                        current = section.getAttribute('id');
                    }
                });
                
                navLinks.forEach(link => {
                    link.classList.remove('active');
                    if (link.getAttribute('href').substring(1) === current) {
                        link.classList.add('active');
                    }
                });
            });
            
            // Calendar functionality
            const today = new Date();
            let currentMonth = today.getMonth();
            let currentYear = today.getFullYear();
            
            const persianMonths = [
                'فروردین', 'اردیبهشت', 'خرداد', 'تیر', 'مرداد', 'شهریور',
                'مهر', 'آبان', 'آذر', 'دی', 'بهمن', 'اسفند'
            ];
            
            function renderCalendar() {
                const calendarGrid = document.getElementById('calendar-grid');
                calendarGrid.innerHTML = '';
                
                // نمایش نام ماه
                document.getElementById('current-month').textContent = 
                    `${persianMonths[currentMonth]} ${currentYear}`;
                
                // ایجاد روزهای تقویم
                const daysInMonth = new Date(currentYear, currentMonth + 1, 0).getDate();
                const firstDay = new Date(currentYear, currentMonth, 1).getDay();
                
                // روزهای خالی اول
                for (let i = 0; i < firstDay; i++) {
                    const emptyDay = document.createElement('div');
                    emptyDay.classList.add('calendar-day', 'empty');
                    calendarGrid.appendChild(emptyDay);
                }
                
                // روزهای ماه
                for (let day = 1; day <= daysInMonth; day++) {
                    const dayElement = document.createElement('div');
                    dayElement.classList.add('calendar-day');
                    dayElement.textContent = day;
                    
                    // برجسته‌سازی رویدادها
                    if (hasEvent(currentYear, currentMonth, day)) {
                        dayElement.classList.add('has-event');
                    }
                    
                    // برجسته‌سازی امروز
                    if (currentYear === today.getFullYear() && 
                        currentMonth === today.getMonth() && 
                        day === today.getDate()) {
                        dayElement.classList.add('today');
                    }
                    
                    calendarGrid.appendChild(dayElement);
                }
            }
            
            function hasEvent(year, month, day) {
                // در حالت واقعی این تابع رویدادها را از سرور دریافت می‌کند
                const eventDays = [15, 22, 27];
                return eventDays.includes(day);
            }
            
            // کنترل‌های تقویم
            document.getElementById('prev-month').addEventListener('click', () => {
                currentMonth--;
                if (currentMonth < 0) {
                    currentMonth = 11;
                    currentYear--;
                }
                renderCalendar();
            });
            
            document.getElementById('next-month').addEventListener('click', () => {
                currentMonth++;
                if (currentMonth > 11) {
                    currentMonth = 0;
                    currentYear++;
                }
                renderCalendar();
            });
            
            // تقویم اولیه
            renderCalendar();
            
            // سیستم تغییر زبان
            document.querySelectorAll('.lang-btn').forEach(btn => {
                btn.addEventListener('click', function() {
                    document.querySelectorAll('.lang-btn').forEach(b => b.classList.remove('active'));
                    this.classList.add('active');
                    
                    const lang = this.dataset.lang;
                    changeLanguage(lang);
                });
            });
            
            function changeLanguage(lang) {
                alert(`زبان به ${lang} تغییر یافت. در نسخه کامل، تمام محتوا ترجمه خواهد شد.`);
            }
            
            // سیستم تغییر حالت تاریک
            const darkModeToggle = document.getElementById('dark-mode-toggle');
            darkModeToggle.addEventListener('change', function() {
                document.body.classList.toggle('dark-theme', this.checked);
                localStorage.setItem('darkMode', this.checked);
            });
            
            // بررسی تنظیمات ذخیره شده کاربر
            if (localStorage.getItem('darkMode') === 'true') {
                document.body.classList.add('dark-theme');
                darkModeToggle.checked = true;
            }
            
            // سیستم احراز هویت
            document.getElementById('scheduleBtn').addEventListener('click', authenticateUser);
            document.getElementById('messageForm').addEventListener('submit', function(e) {
                e.preventDefault();
                authenticateUser();
            });
            
            // سیستم تحلیل‌ها برای کاربران احراز هویت شده
            function checkAuthForAnalytics() {
                const isAuthenticated = localStorage.getItem('faceAuth') === 'true';
                if (isAuthenticated) {
                    document.getElementById('analytics').style.display = 'block';
                    initAnalyticsDashboard();
                }
            }
            
            function initAnalyticsDashboard() {
                // ایجاد نمودار با Chart.js
                const ctx = document.getElementById('engagement-chart').getContext('2d');
                new Chart(ctx, {
                    type: 'line',
                    data: {
                        labels: ['۱', '۵', '۱۰', '۱۵', '۲۰', '۲۵', '۳۰'],
                        datasets: [{
                            label: 'بازدیدها',
                            data: [120, 190, 150, 220, 180, 200, 240],
                            borderColor: '#1a73e8',
                            tension: 0.3,
                            fill: true
                        }, {
                            label: 'دانلودها',
                            data: [40, 60, 55, 80, 75, 90, 110],
                            borderColor: '#4caf50',
                            tension: 0.3,
                            fill: true
                        }]
                    },
                    options: {
                        responsive: true,
                        plugins: {
                            legend: {
                                position: 'top',
                            }
                        }
                    }
                });
            }
            
            // تابع احراز هویت چهره‌ای (شبیه‌سازی شده)
            function authenticateUser() {
                return new Promise((resolve) => {
                    // نمایش مدال احراز هویت
                    const authModal = document.createElement('div');
                    authModal.id = 'auth-modal';
                    authModal.innerHTML = `
                        <div class="modal-content">
                            <h3>تأیید هویت چهره‌ای</h3>
                            <div class="camera-feed">
                                <div class="placeholder-camera" style="background: linear-gradient(45deg, #1a237e, #4fc3f7); height: 100%; display: flex; align-items: center; justify-content: center; color: white; font-size: 3rem;">
                                    <i class="fas fa-camera"></i>
                                </div>
                                <div class="face-indicator">👤</div>
                            </div>
                            <div class="instructions">
                                <p>لطفاً صورت خود را در مرکز قاب قرار دهید</p>
                            </div>
                            <button id="cancel-auth">لغو</button>
                        </div>
                    `;
                    document.body.appendChild(authModal);
                    
                    // شبیه‌سازی فرآیند احراز هویت
                    setTimeout(() => {
                        authModal.remove();
                        
                        // در اینجا احراز هویت موفق فرض می‌شود
                        localStorage.setItem('faceAuth', 'true');
                        alert('احراز هویت با موفقیت انجام شد! دسترسی کامل فعال گردید.');
                        
                        // فعال‌سازی بخش تحلیل‌ها
                        checkAuthForAnalytics();
                        
                        resolve(true);
                    }, 3000);
                    
                    // مدیریت لغو احراز هویت
                    document.getElementById('cancel-auth').addEventListener('click', () => {
                        authModal.remove();
                        resolve(false);
                    });
                });
            }
        });
    </script>
</body>
</html>

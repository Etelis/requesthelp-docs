---
layout: default
title: Feature Tree
nav_order: 4
---

# Feature Tree

```json
{
  "robot_help_reasons": {
    "robot_related": {
      "physical_inability": {
        "height_limitation": {
          "description": "The robot's physical height limits its ability to perform certain tasks.",
          "examples": ["Not tall enough to reach elevator buttons"],
          "source": "Previous Study"
        },
        "manipulator_limitation": {
          "description": "The robot's manipulators are not designed for certain tasks due to height or precision requirements.",
          "examples": ["Manipulators not designed for pressing elevator buttons"],
          "source": "Previous Study"
        }
      },
      "physical_obstacles": {
        "description": "The robot encounters physical obstacles that it cannot navigate around or over.",
        "examples": ["Stairs", "Closed doors", "High thresholds"],
        "source": "Generated"
      },
      "malfunction": {
        "mechanical_failure": {
          "description": "The robot experiences mechanical issues that prevent it from functioning correctly.",
          "examples": ["Broken wheel", "Arm malfunction", "Sensor failure"],
          "source": "Generated"
        },
        "power_depletion": {
          "description": "The robot's power supply is depleted and it needs assistance to recharge or replace batteries.",
          "examples": ["Low battery", "Disconnected power supply"],
          "source": "Generated"
        }
      },
      "technical_issues": {
        "software_errors": {
          "description": "The robot experiences software errors that prevent it from functioning correctly.",
          "examples": ["Software bugs", "System crashes", "Connectivity issues"],
          "source": "Generated"
        },
        "data_issues": {
          "description": "The robot encounters data issues that affect its operations.",
          "examples": ["Corrupted data", "Incorrect data input", "Data loss"],
          "source": "Generated"
        },
        "interference": {
          "description": "The robot experiences interference from external sources that disrupt its operations.",
          "examples": ["Electromagnetic interference", "Signal jamming", "Radio frequency interference"],
          "source": "Generated"
        }
      },
      "cognitive": {
        "navigation_errors": {
          "description": "The robot experiences errors in its navigation system, leading to incorrect movements or getting lost.",
          "examples": ["GPS signal loss", "Path planning failure", "Incorrect mapping"],
          "source": "Generated"
        },
        "missing_data": {
          "description": "The robot lacks the necessary data to complete the task.",
          "examples": ["Does not know the location of an object", "Lacks information about the environment"],
          "source": "Generated"
        },
        "planning": {
          "decision_making": {
            "description": "The robot struggles with making decisions in complex scenarios.",
            "examples": ["Cannot choose the best path", "Difficulty prioritizing tasks"],
            "source": "Generated"
          },
          "processing_speed": {
            "description": "The robot's processing speed is too slow to react in real-time.",
            "examples": ["Delayed response to commands", "Slow adaptation to changes"],
            "source": "Generated"
          }
        }
      }
    },
    "environmental": {
      "environment_related": {
        "environmental_conditions": {
          "description": "The robot is in an environment where conditions are beyond its operational limits.",
          "examples": ["Extreme temperatures", "Wet or slippery surfaces", "Dusty or dirty environments"],
          "source": "Generated"
        }
      },
      "consequence": {
        "costly_alternative_plan": {
          "description": "The robot highlights the high cost of alternative plans if not helped.",
          "examples": ["May be stuck for hours", "Waiting for another helper might take time"],
          "source": "Previous Study"
        },
        "harm_prevention": {
          "description": "The robot communicates that assisting it will help prevent potential harm.",
          "examples": ["Preventing accidents", "Avoiding hazards", "Ensuring safe operation"],
          "source": "Survey Conclusion"
        },
        "safety_assurance": {
          "description": "The robot assures bystanders that it is safe to help.",
          "examples": ["Safety certifications", "Reassuring messages", "Demonstrating safe behavior"],
          "source": "Survey Conclusion"
        }
      }
    },
    "task": {
      "robot_task": {
        "task_ease": {
          "description": "The robot ensures that helping it is easy for bystanders.",
          "examples": ["Minimal effort required", "Clear and simple instructions", "Low physical exertion"],
          "source": "Survey Conclusion"
        },
        "task_complexity": {
          "description": "The complexity of the task affects the likelihood of receiving help.",
          "examples": ["Simple tasks like picking up an object", "Complex tasks like troubleshooting technical issues"],
          "source": "Generated"
        },
        "task_urgency": {
          "description": "The urgency of the task influences the willingness to help.",
          "examples": ["Immediate assistance needed", "Can wait for a convenient time"],
          "source": "With a Little Help of Humans. An Exploratory Study of Delivery Robots Stuck in Snow"
        },
        "task_importance": {
          "description": "The importance of the task can impact the decision to help.",
          "examples": ["Critical tasks like delivering medicine", "Non-critical tasks like delivering a package"],
          "source": "With a Little Help of Humans. An Exploratory Study of Delivery Robots Stuck in Snow"
        },
        "task_nature": {
          "description": "The nature of the task can impact the decision to help.",
          "examples": ["Routine tasks", "Emergency tasks", "Specialized tasks"],
          "source": "Generated"
        },
        "task_familiarity": {
          "description": "The helper's familiarity with the task affects their willingness to assist.",
          "examples": ["Common household tasks", "Technical tasks requiring specific knowledge"],
          "source": "Generated"
        },
        "situation_visibility": {
          "description": "How visible the task is to potential helpers can influence the likelihood of receiving help.",
          "examples": ["Public tasks", "Private tasks"],
          "source": "Generated"
        }
      },
      "user_task": {
        "task_safety": {
          "description": "The robot assures that providing help is safe.",
          "examples": ["No risk in helping", "Helping is completely safe"],
          "source": "Previous Study"
        },
        "level_of_interruption": {
          "description": "The robot emphasizes the minimal interruption to the helper.",
          "examples": ["Only takes a few seconds"],
          "source": "Previous Study"
        },
        "capability_assurance": {
          "description": "Requests should be tailored to the perceived capabilities of the helpers, ensuring they feel capable of providing assistance.",
          "examples": ["Simple tasks", "Clear instructions", "Confidence-building statements"],
          "source": "Needy Robots - Designing Requests for Help Using Insights from Social Psychology"
        },
        "cost_benefit_analysis": {
          "description": "Requests for assistance should minimize the cost to the helper while highlighting the benefits.",
          "examples": ["Short duration tasks", "Offering gratitude or rewards", "Explaining the importance of the task"],
          "source": "Needy Robots - Designing Requests for Help Using Insights from Social Psychology"
        }
      }
    },
    "user": {
      "social": {
        "diffusion_of_responsibility": {
          "description": "The robot counters the diffusion of responsibility in public places.",
          "examples": ["Directly addressing individuals", "Clarifying that specific help is needed", "Reducing ambiguity"],
          "source": "Survey Conclusion"
        },
        "social_influence_and_norms": {
          "description": "The robot appeals to social influences and norms to encourage help.",
          "examples": ["Encouraging others to help", "Helping is a good deed"],
          "source": "Previous Study"
        }
      },
      "emotional": {
        "pity": {
          "description": "The robot induces a sense of pity to encourage help from bystanders.",
          "examples": ["Operator will be disappointed", "Many people walked by without helping"],
          "source": "Previous Study"
        },
        "usefulness_assurance": {
          "description": "The robot communicates that it is performing a useful job.",
          "examples": ["Assisting with community services", "Providing important deliveries", "Supporting public safety"],
          "source": "Survey Conclusion"
        },
        "communication_clarity": {
          "description": "The robot clearly communicates its need for help and the specific assistance required.",
          "examples": ["Clear speech", "Simple instructions", "Visual cues"],
          "source": "Generated"
        }
      }
    }
  }
}

```